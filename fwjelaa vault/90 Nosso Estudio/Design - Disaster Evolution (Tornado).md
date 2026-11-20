---
tags: [design, disaster-evolution, tornado, decisao]
data: 2026-11-20
fonte: pedido do usuário (20/11) + [[Plano MVP - Disaster Evolution]] (substitui a parte do Fogo)
---
# Design — Disaster Evolution: você é o tornado
**Em uma frase:** você é um tornado — destrói a cidade para crescer, faz rebirth para voltar mais forte e engole tornados menores.

Pedido do usuário: ser o tornado; evoluir destruindo coisas do mapa; rebirth volta ao tornado zero com buff para crescer muito mais rápido; PvP entre tornados (maior mata menor, clique ataca, **Q = especial que depende do nível**); ao morrer **só a barra de progresso zera, o nível fica**. O mapa e os modelos ficam para depois.

## Decisões que eu tomei (dá para mudar)
| Tema | Decisão |
|---|---|
| Controle | Seu personagem **vira** o tornado (corpo invisível, tornado no lugar). Anda com WASD/analógico; velocidade e tamanho crescem com o nível. |
| Destruir | O servidor confere a cada 0,2 s o que está dentro do raio do tornado e dá dano. Construção grande tem muita vida: só tornado grande derruba rápido (meta natural). |
| Progresso | Destruir dá **XP** proporcional ao tamanho da construção. A barra enche → **sobe de nível**. |
| Níveis | **Atualizado 20/11 (noite):** máximo 15 + 1 por rebirth até 30; subir é na mão (EVOLVE, tecla R); formas novas Typhoon 19, Firenado 23, Void Storm 27; Hurricane no 15. **Antes:** 1 a 16. **Formas**: Brisa (1) → Redemoinho (4) → Tornado (8) → Supertornado (12) → Furacão (16). Cada forma muda o visual e libera um Q novo. (Plano antigo era 1–50 com forma a cada 10.) |
| Rebirth | No nível 16: volta ao nível 1 com **+50% de XP por rebirth** (1º = ×1,5, 2º = ×2…) e +10% de dano. Visual do tornado muda de cor a cada rebirth (status). |
| Vida (PvP) | Cada tornado tem vida que cresce com o nível. |
| Encostar | Tornado **5+ níveis maior** que encosta num menor causa dano contínuo nele (engolir). Iguais ou parecidos não se machucam só por encostar. |
| Clique (M1) | Rajada curta na frente: dano em tornados e construções. Recarga 0,6 s. |
| Q (especial por forma) | Redemoinho: **investida** (dash). Tornado: **sucção** (puxa tornados menores e destroços). Supertornado: **chuva de destroços** (arremessa em área). Furacão: **tempestade** (área grande por 4 s). Recarga 8–15 s. |
| Morrer | **Zera só a barra** do nível atual (o nível fica). Renasce no ponto inicial com **escudo de 5 s**. |
| Matar | Quem mata ganha XP = 25% da barra do nível da vítima (incentiva caçar, mas sem roubar o nível). |
| Proteção | **Sem área segura** (decisão 20/11). Só o escudo de 5 s ao nascer e de 2 s ao subir de nível. Mais tarde o mapa separa pequenos e grandes por regiões. |
| Cidade | Construção destruída **volta depois de ~60 s** (para 6 jogadores nunca ficarem sem o que destruir). |
| Salvo | Nível, XP, rebirths. |
| Dinheiro/loja | **Fora do MVP.** A progressão é só XP. Monetização entra na fase 5 (passe 2× XP, Q extra, cores de tornado). |

## O que o código atual já tem
- Busca de construções por raio no servidor (`CityService.query`) + dano com autoridade (`CityService.hit`), cidade montada no cliente, destroços e qualidade para celular.
- Efeito de tornado do Vento (nível 4) que pode virar o visual do jogador.
- Falta: personagem-tornado, XP/níveis/formas, salvar, rebirth, PvP (vida, M1, Q, morte), **cidade voltar** (hoje construção destruída fica destruída).
- Sai do jogo: o Fogo/Raio/Vento como "magias" de clique (`ElementInput`/hotbar) e a vitória da partida.

## Fases
1. **Tornado jogável:** personagem vira tornado, anda, destrói o que encosta, ganha XP, sobe de nível, cresce. Barra de XP na tela.
2. **Salvar + rebirth.**
3. **PvP:** vida, encostar, clique, Q da 1ª forma, morte zerando a barra, escudo. **Sem área segura** (20/11): no lugar, mapa separado por regiões (pequenos x grandes), depois. Servidor de **6 jogadores**. PvP equilibrado entre níveis parecidos.
4. **Cidade volta** (regeneração) + Q das outras formas.
5. **Monetização + página do jogo** (vídeo, thumbnails) → lançar.
