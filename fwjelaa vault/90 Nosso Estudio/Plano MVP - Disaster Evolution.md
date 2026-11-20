---
tags: [plano, mvp, disaster-evolution, decisao]
data: 2026-11-20
fonte: código do repositório DestroytheCity (branch carlos) + [[melhores-tecnicas]] + [[Disaster Evolution - concorrencia]]
---
# Plano MVP — Disaster Evolution
> **Desatualizado (20/11):** o jogo virou **tornado**, não Fogo — ver [[Design - Disaster Evolution (Tornado)]] e o status em [[Contexto - Disaster Evolution]]. Daqui ainda valem: a regra ENTRA/DEPOIS, "Pronto para lançar quando…" e "Medir na 1ª semana".

**Em uma frase:** você é um desastre — começa como uma faísca, cresce destruindo a cidade e evolui até virar um inferno.

**Regra:** só entra no lançamento o que está na lista "ENTRA". Ideia nova vai para "DEPOIS". Prazo: **lançar em até 10 dias de trabalho**.

## Decisões de base
- **Uma linha de desastre: Fogo** (é o elemento mais visual e o mais rápido no simulador). Raio e Vento viram as atualizações das semanas 2 e 3.
- **Um lugar só** (sem lobby nem teleporte); servidor de **8 jogadores**; todo mundo na mesma cidade, que se regenera.
- **Público:** lançar para todos, mas planejar os anúncios para chegar aos **100 jogadores engajados** (trava dos menores de 16, ver [[Trava de idade - 100 jogadores engajados]]).
- **Progresso salvo** (não zera a cada partida).

## O loop (com as metas dos estudos)
1. Nasce na borda da cidade **já como faísca**, com uma seta para a 1ª casa → destrói em < 30 s.
2. Destruir dá **Poder** (+ a cada construção) e **Dinheiro**; o Poder também sobe +1 por segundo jogando.
3. **Evolução** quando o Poder passa de um marco: Faísca → Bola de Fogo → Incêndio (espalha) → Onda de Calor → **Inferno**. Os 5 níveis do Fogo **já existem no código**. Meta: 1ª evolução em ~2 min, a 2ª em ~5 min, e as seguintes a cada 10–15 min.
4. **Upgrades com dinheiro** (dano, raio, recarga). O 1º sai em < 5 min; botão **"Comprar máximo"**.
5. **Construções fortes** (prédios altos) só caem com formas maiores: é a meta visível ("desbloqueia no Incêndio").
6. **Rebirth** no Inferno: volta a Faísca com **multiplicador ×1,5** + um visual novo de fogo. Isso é o motivo de longo prazo.
7. **Cidade regenera** bairro por bairro (~60 s depois de destruído), para nunca faltar o que destruir com 8 pessoas.

## ENTRA no lançamento
| # | Item | Status no código | O que fazer |
|---|---|---|---|
| 1 | Cidade montada no cliente + estado no servidor (Garden Village) | ✅ existe (`CityGen`, `CityWorld`, `CityState`, `CityService`) | Usar como está |
| 2 | Fogo com 5 níveis que mudam a mecânica + efeitos | ✅ existe (`ElementConfig`, `ElementPlan`, `ElementService`, `ElementFx`) | Ligar o nível ao Poder (hoje é por `setLevel`/dev) |
| 3 | Destroços e níveis de qualidade para celular | ✅ existe (`Wreck`, `WreckPresenter`, `QualityTier`, `LodManager`) | Usar como está |
| 4 | Poder, evolução por marcos, +1/s | ❌ novo | Módulo puro `Logic/Evolution` + Config + testes; servidor aplica o nível |
| 5 | Dinheiro persistente + upgrades + "Comprar máximo" | 🟡 parcial (`PlayerData.Coins`, `MatchService.pay`) | Upgrades novos (Config + lógica pura); dinheiro passa a ser salvo |
| 6 | Construções fortes exigem forma mínima | 🟡 parcial (havia `UnderPower` no sistema antigo) | Regra simples por tier de prédio na lógica de dano |
| 7 | Regeneração por bairro | ❌ novo | `CityState` marca bairro destruído → timer → reconstrói (snapshot já existe para quem entra) |
| 8 | Rebirth (×1,5, visual de fogo novo) | ❌ novo | Usar o módulo pronto de rebirth do fwjelaa (`fwjelaa-systems`) adaptado |
| 9 | Salvar progresso (Poder, nível, dinheiro, upgrades, rebirths) | 🟡 `PlayerData` existe | Novos campos + migração; checar com `fwjelaa-datastore-safety` |
| 10 | Recompensa diária que **acumula** (sem zerar) | 🟡 existe com `Streak` | Tirar o "zera se faltar"; prêmios no dia 1, 3 e **7** |
| 11 | Placar do servidor ("maior desastre") | ❌ novo | Módulo pronto de leaderboard do fwjelaa |
| 12 | HUD: barra de Poder com o próximo marco, dinheiro, botão de upgrade/rebirth | 🟡 base pronta (`UiLayout`, `Style`, `Screens`, `Feedback`) | Telas novas no padrão atual; testar no celular curto |
| 13 | Início em < 60 s: nascer como faísca + seta para a 1ª casa | 🟡 `GuidePath` existe | Ligar ao spawn; sem tutorial em texto |
| 14 | Monetização: **passe 2× Poder**, **passe disparo automático**, **consumível "Evolução instantânea"**, **pacote inicial ~49 Robux** | 🟡 `StoreService` + recibos existem | Produtos novos; preços casados com os pacotes de Robux; checar com `fwjelaa-monetization-compliance` |
| 15 | Bônus de amigo (+10% Poder com amigo no servidor) | ❌ novo | Pequeno: checar `IsFriendsWith` ao entrar |
| 16 | Segurança: lançar só pelo servidor, com limite por segundo | ✅ existe (`RateLimit`, validação de mira) | Revisar com `fwjelaa-secure-remotes` |
| 17 | Página do jogo: **vídeo de gameplay**, 5 thumbnails, ícone, nome "+1 Disaster Evolution"-like próprio | ❌ novo | Gravar no Studio; thumbnails com a cidade em chamas |

## SAI (não apagar do git; só desligar/remover do place)
Lobby, `PartyService`, `Teleporter`, `RunStore`, matchmaking planejado, partida com fim (`victory`/marcos da partida), loja de rastros, pacotes de gemas, Raio e Vento **no lançamento**, Harbor e Metropolis, LOD/pipeline do Blender.

## DEPOIS (por ordem, com base nas métricas)
1. **Semana 2:** linha **Raio** (escolhida no rebirth) + evento de fim de semana "Tempestade" (2× Poder).
2. **Semana 3:** linha **Vento** (tornado) + 2ª cidade (praia).
3. Desastres raros sorteados (Meteoro) com probabilidades à mostra; missões diárias; trocas ou clãs se o D7 pedir.

## Pronto para lançar quando…
- [ ] Jogando em < 60 s numa conta nova; 1º upgrade em < 5 min (cronometrado)
- [ ] 30+ FPS no emulador do Studio em celular no Tier Baixo, com 4 jogadores destruindo
- [ ] Progresso salvo e recuperado após sair e voltar (teste)
- [ ] Compras testadas no Studio (concede e não duplica)
- [ ] Testes do pipeline passando (`lune run check`)
- [ ] Vídeo + thumbnails + ícone na página
- [ ] Update da semana 2 escrito

## Medir na 1ª semana
Bounce (0–60 s e 61–180 s), tempo médio de sessão (meta > 10 min com anúncio, > 20 vindo da Home), D1 (meta 12–15%), funil do início (Player Funnel), conversão de compra. Orçamento: fases de [[melhores-tecnicas]] (grátis → teste de US$ 30–50 → escala só com métricas boas).

## Ordem de trabalho (≈10 dias)
1. Desligar lobby/party/partida com fim; um place só; spawn na cidade.
2. Poder + evolução + upgrades (lógica pura + testes) e ligação ao Fogo.
3. Persistência (PlayerData) + diária acumulativa.
4. Regeneração por bairro + construções fortes.
5. HUD + início em 60 s.
6. Rebirth + placar (módulos do fwjelaa).
7. Monetização + bônus de amigo.
8. Teste no celular/emulador com 4 contas; ajuste de números.
9. Página do jogo (vídeo, thumbnails) e lançamento.
