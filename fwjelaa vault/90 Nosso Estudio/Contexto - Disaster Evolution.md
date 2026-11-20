---
tags: [contexto, disaster-evolution, tornado, status]
data: 2026-11-20
fonte: movido de `Documents\DisasterEvolution\CONTEXTO.md` (20/11)
---
# Contexto — Disaster Evolution (para continuar num chat novo)
> No chat novo: peça "lê o Contexto - Disaster Evolution no Obsidian e continua". Atualizado em 20/11/2026.

## O jogo
Você é um **tornado**: destrói a cidade para ganhar XP, sobe de nível (cresce), faz **rebirth no nível 16** (volta ao 1 com +50% XP e +10% dano por rebirth) e luta com outros tornados (PvP).
Design completo: [[Design - Disaster Evolution (Tornado)]] (decisões de PvP, Q por forma, morte zera só a barra etc.). O [[Plano MVP - Disaster Evolution]] é da versão Fogo; vale só a parte de lançamento/métricas.

## Projeto
- Pasta: `C:\Users\Win11-User\Documents\DisasterEvolution` (git próprio, sem remote). Base copiada do Destroy the City, **um place só** (papel "Run"), sem lobby/party/teleporte.
- Rojo: `ligar-rojo.bat` → porta **34874**. Place no Studio: "Experiência sem título" (placeId 96242379546184).
- Pipeline: `lune run check` (ou `lune run check fix`) = Rojo build + testes + Selene + StyLua. Último: **1090 testes, 0 falhas, tudo OK**.
- Regras: lógica pura em `src/shared/Logic` com testes em `tests/`; números em `src/shared/Config`; o hook do fwjelaa confere cada .luau escrito.

## Feito (fase 1 — tornado jogável)
- `shared/Config/TornadoConfig.luau` + `shared/Logic/Tornado.luau` + `tests/Tornado.spec.luau`: XP por nível (base 8 × 1,38^(L-1)), raio/dano/velocidade por nível, 5 formas (Breeze 1, Dust Devil 4, Tornado 8, Supertornado 12, Hurricane 16), rebirth.
- `server/Match/TornadoService.luau`: a cada 0,2 s dá dano no que está no raio (CityService.query/hit) e paga XP; esconde o corpo (Transparency no servidor); grupos de colisão "Tornado" x "CityBuildings" (atravessa construções, pisa no chão).
- `client/City/TornadoClient.luau`: visual do tornado (fitas em espiral com Beams, fumaça orbitando em 4 alturas, poeira, detritos, nuvem no topo; partículas caem com a qualidade e para os outros), marca a cidade no grupo de colisão, barra de XP no topo.
- Saíram `ElementInput`/`ElementBar` (lançar magia com clique).
- **Testado no Studio:** corpo some, tornado atravessa casas, XP sobe destruindo.

## Feito (fase 2 — salvar + rebirth), 20/11 — código pronto, **falta testar no Studio**
- `server/PlayerData.luau` reescrito no load/save: `UpdateAsync` com **trava de sessão** (`shared/Logic/Lease.luau`, 90 s, renovada no autosave a cada 30 s espalhado), load com 3 saídas (pronto / travado / falhou) — **load que falhou nunca salva** (antes salvava o padrão por cima do save real); no jogo publicado expulsa com mensagem, no Studio joga sem salvar. `Schema = 2` (save mais novo é recusado). Store novo `DisasterEvolution_PlayerData_v1`; **Studio usa `..._Studio`** (teste nunca mexe no save real). Saída e BindToClose salvam e soltam a trava (BindToClose em paralelo, até 25 s).
- Salva **Level, Xp, Rebirths** (limpos por `Tornado.sanitize` ao carregar). `PlayerData.setTornado` é o único jeito de mudar o progresso; o `TornadoService` usa ele.
- Rebirth: remote `Rebirth` (RemoteFunction); o servidor confere o nível máximo (16), volta ao 1 com +1 rebirth e salva na hora. Botão verde "REBIRTH +50% XP" abaixo da barra de XP, só aparece no nível 16; a barra mostra "· R2" etc.
- Pipeline: **1094 testes, 0 falhas**, Selene 0/0, StyLua OK (novos: `tests/Lease.spec.luau`, sanitize no `Tornado.spec.luau`).
- **Como testar:** ligar Game Settings → Security → *Enable Studio Access to API Services*. Jogar, subir uns níveis, Stop, Play de novo → o nível volta. Para testar o rebirth sem jogar até o 16, na barra de comando (servidor): `require(game.ServerScriptService.Server.PlayerData).setTornado(game.Players:GetPlayers()[1], 16, 0, 0)`.

## Feito (fase 3 — PvP), 20/11 — código pronto, **falta testar no Studio (com 2 jogadores)**
- Decisões do usuário: **escudo de 2 s ao subir de nível**; no celular os botões de ataque ficam **junto do pulo** (exceção à regra antiga "nada no lado direito"). **Rebirth leva de volta ao spawn** (`MatchService.toSpawn`).
- Números em `shared/Config/PvpConfig.luau`, fórmulas em `shared/Logic/Pvp.luau` (testes em `tests/Pvp.spec.luau`). Servidor: `server/Match/PvpService.luau`. Cliente: `client/City/PvpClient.luau`.
- Vida própria (atributos `Hp`/`MaxHp`, 100 no nível 1, ×1,2 por nível), regenera 5%/s depois de 4 s sem levar dano. Muda de nível = mantém a % de vida.
- Encostar: 5+ níveis maior engole (50% da vida da vítima por segundo, ~2 s).
- Rajada (clique na direção do mouse; botão BLAST no celular): cone ~120° à frente, recarga 0,6 s, 12% da vida máxima de quem ataca; também quebra construções na frente (dá XP).
- Q (a partir da 2ª forma, nível 4): investida 110 studs/s por 0,5 s, recarga 8 s, 25% da vida de quem ataca em cada tornado atropelado. O cliente dá o impulso; o servidor confere forma/recarga e dá o dano.
- Morte: só a barra de XP zera (nível fica), quem matou ganha 25% da barra do nível da vítima; renasce no spawn com escudo de 5 s. Atacar tira o próprio escudo. Morto não destrói a cidade.
- **Sem área segura** (decisão do usuário, 20/11). PvP **equilibrado entre níveis parecidos**: rajada e Q funcionam entre todos; mesmo nível = mesma vida e mesmo dano (9 rajadas para matar), 1 nível acima = 7 contra 10 rajadas (teste em `Pvp.spec.luau`). Só o "engolir encostando" exige 5+ níveis de diferença.
- Escudo = **bolha de ForceField em volta do tornado** (todos veem, pisca no último segundo; pedido do usuário no lugar do texto "SHIELD"). HUD: barra de vida abaixo da barra de XP (fica azul com escudo), rebirth desceu para o topo 128. Em cima dos outros: "LV n" + vida (vermelho = ele te engole, verde = você engole ele). Botão Q (roxo; cinza com "Q · LV4" ou recarga).
- Pipeline: **1102 testes, 0 falhas**, Selene 0/0, StyLua OK.
- **Como testar:** Studio → Test → Clients and Servers com 2 jogadores. Para ter diferença de nível: `require(game.ServerScriptService.Server.PlayerData).setTornado(game.Players:GetPlayers()[1], 8, 0, 0)`.
- **Servidor de 6 jogadores** (decisão do usuário, para o mapa não precisar ser gigante). Não dá para mudar por script: Creator Hub → a experiência → Places → o place → **Server size = 6** (ou Studio → Game Settings → Places). Precisa o jogo estar publicado.

## Feito (fase 4 — cidade volta + Q das outras formas), 20/11 — código pronto, **falta testar no Studio**
- Escudo sem nenhuma UI (pedido do usuário): só a bolha em volta do tornado.
- **Regeneração:** construção destruída volta inteira depois de `MatchConfig.RegenSeconds` = 60 s. Servidor: fila em `CityService` (`regenerate()` antes de cada lote) + `CityState.revive`; o lote CityDelta leva a volta e o cliente remonta o modelo (`CityClient.restoreBuilding`, `LodManager.revive` tira os destroços). Snapshot de quem entra também reconstrói. Testes: `tests/Regen.spec.luau`. A vitória antiga não dispara mais pelo tornado.
- **Q por forma** (`Pvp.special`: o Q é o da maior forma liberada; números em `PvpConfig`, todos proporcionais a quem ataca):
  - Dust Devil (nv 4) **Dash**: investida (já existia). Recarga 8 s.
  - Tornado (nv 8) **Pull**: 1,5 s puxando tornados **menores** num raio 2,5× o do tornado (remote `Knock`: o cliente da vítima se move), 12%/s de dano, quebra a cidade em volta. Recarga 10 s.
  - Supertornado (nv 12) **Debris**: golpe único em área (2× o raio), 30% da vida máxima de quem ataca + 2 s de dano na cidade. Recarga 12 s.
  - Hurricane (nv 16) **Storm**: 4 s de área (2,5× o raio), 15%/s em todos + dano na cidade. Recarga 15 s.
  - Efeitos (`SpecialFx`, todos veem): anel que fecha (Pull), blocos caindo (Debris), disco escuro girando (Storm). Botão Q mostra o nome: "Q DASH / PULL / DEBRIS / STORM".
- Pipeline: **1106 testes, 0 falhas**, Selene 0/0, StyLua OK.
- Testar: setTornado com nível 8/12/16 e apertar Q; destruir uma casa e esperar 60 s.

## Mudanças de 20/11 (noite) — pedidos do usuário, **falta testar no Studio**
- **Vida própria** embaixo no centro (onde era o UPGRADES do Destroy the City): painel "HP atual/máx". Escudo só a bolha.
- **Nível máximo = 15 + rebirths, até 30** (15 rebirths; depois do 30 não tem mais rebirth). Save antigo é limpo para o máximo dos rebirths (`Tornado.sanitize`).
- **Subir de nível é na mão:** o XP junta além da barra; aparece o botão **"R EVOLVE"** (verde) abaixo da barra e a tecla **R** sobe 1 nível (remote `Evolve`, servidor confere). No máximo com a barra cheia o botão vira **"R REBIRTH!"** (amarelo) e abre a **janela de confirmação** (rebirths, XP/dano antes >> depois, nível máximo +1, forma nova liberada, o que fica e o que zera; botão REBIRTH). Referência visual: prints de outro jogo que o usuário mandou (só o layout, nada copiado).
- Barra de XP: `LV 12/15 · forma · XP/precisa`. Morrer zera a barra (inclusive o XP guardado além dela — incentivo a evoluir logo).
- **Formas novas** (escolha do Claude): Breeze 1, Dust Devil 4, Tornado 8, Supertornado 12, **Hurricane 15** (último Q, Storm), **Typhoon 19**, **Firenado 23**, **Void Storm 27** (as 3 últimas só com rebirth; usam o Q Storm).
- **Atenção (não calibrado):** XP até o 30 é ~240 mil sem bônus; raio no 30 ≈ 52 studs, dano ≈ 19 mil/s. Ajustar `TornadoConfig` depois de testar.
- Pipeline: **1107 testes, 0 falhas**.

## Skills (Q) — uma por forma (pedido do usuário, 20/11) — **falta testar no Studio**
- Decisões: acertam **cidade + tornados** (dano proporcional a quem usa); **visual simples agora**, passe de VFX depois; o clique (rajada) continua.
- Motor único de "zonas": `shared/Config/SkillConfig.luau` (as 8 skills, tudo em raios do tornado), `shared/Logic/Skills.luau` (zonas por tempo, igual no servidor e no cliente; testes `tests/Skills.spec.luau`), `server/Match/SkillService.luau` (dano, puxar/empurrar via `PvpService.knock`, rastro, explosão final que cresce com o destruído), `client/City/SkillFx.luau` (coluna girando + disco + blocos "arrastados", fogo, explosão). O Q antigo (Dash/Pull/Debris/Storm no `PvpService`) saiu.
- Q mira no mouse (PC) ou na câmera (celular). Botão Q mostra o nome da skill e a recarga.
- Skills: 1 Breeze **Wind Burst** (linha curta, empurra, acerta 1x) · 4 Dust Devil **Dust Dash** (redemoinho em linha, estoura no fim) · 8 Tornado **Vortex Slam** (suga em volta 2,5 s e explode) · 12 Supertornado **Twin Cyclones** (2 tornados orbitando 4 s, voltam e explodem) · 15 Hurricane **Eye of the Storm** (área parada 5 s, puxa, estoura) · 19 Typhoon **Tidal Surge** (onda em linha que arrasta) · 23 Firenado **Inferno Spiral** (fogo em zigue-zague, rastro de fogo 3 s, explode) · 27 Void Storm **Black Hole** (à frente, cresce, puxa forte, implode).
- Limite: "arrastar carros/jogar destroços" é só visual (a cidade é dado no servidor).
- Pipeline: **1112 testes, 0 falhas**.

## Comandos de chat para teste (20/11)
`server/Match/DevCommands.luau` (TextChatCommand). Só no Studio ou para o dono do jogo (`game.CreatorId`). Resposta aparece como aviso na tela.
`/lvl N` · `/max` (máximo dos seus rebirths, barra cheia) · `/xp N` · `/rebirths N` · `/heal` · `/kill` · `/shield N` · `/cd` (zera recargas) · `/spawn` · `/regen` (cidade volta toda) · `/help`.
Se o jogo for de grupo, o dono não é um usuário: aí só funciona no Studio (ajustar `allowed` se precisar).

## Pendente / próximo
0. **Da análise dos 100 vídeos ([[Videos x Disaster Evolution]], 20/11):** o tornado/PvP/skills **não têm som nem tremida** (`client/Feedback.luau` só é usado pela UI antiga) — é o ponto que mais vídeos repetem. Também faltam cor por rebirth e placar do maior tornado; rebirths 1–3 só dão multiplicador (risco). Lista ordenada no fim da nota.
0b. **Monetização (fase 5):** proposta de produtos, preços e lugares em [[Monetizacao - Disaster Evolution]] — discutir com o usuário antes de implementar.
1. **Conferir o visual novo do tornado no Studio** (o último print saiu todo cinza — provavelmente o Studio sem desenhar o 3D, não confirmado). Se a câmera ficar dentro da fumaça, afastar a câmera conforme o tamanho (`CameraController` empurra para 38 e libera 8).
2. **Testar as fases 2 e 3 no Studio** (acima).
3. **Depois (pedido do usuário):** mapa grande o bastante e **separado por regiões**, para tornados pequenos e grandes crescerem longe uns dos outros (no lugar da área segura). Pensar junto com o tamanho de 6 jogadores.
4. **Fase 5:** monetização + página do jogo. Limpar a UI antiga (dinheiro, gemas, UPGRADES, LOBBY, "% DESTROYED", janela CREATE PARTY, loja de rastros).
- Nada commitado desde a base (commit `1ed910c`); perguntar antes de commitar.
- Modelos 3D da cidade: copiar `ReplicatedStorage.Assets` do place do Destroy the City (senão usa blocos).
