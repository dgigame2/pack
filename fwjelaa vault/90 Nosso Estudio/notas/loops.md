# Gameplay loops — notas de pesquisa

Escopo: core loop, loops de progressão, compulsion loop e economia simples, aplicados a jogos Roblox pequenos (simuladores, tycoons, incrementais, RNG). Evidência geral: fraca a média. A maior parte das fontes é opinião ou anedota; quase não há dados públicos com números.

## Técnicas (técnica — mecanismo — evidência — fonte)

- **Core loop em três partes** — o loop é (1) interação minuto a minuto, (2) o conjunto de ações mais repetido, (3) um motor de progressão que move o jogador adiante. Sem o motor, o jogo vira repetitivo e raso. — Mecanismo: separa o que se repete do que dá sentido à repetição. — Evidência: **média** (documentação oficial, sem dados). — https://create.roblox.com/docs/production/game-design/core-loops

- **Progressão amplifica o loop, não o substitui** — XP, níveis e lojas multiplicam uma ação que já é satisfatória; não criam retenção sozinhos. — Mecanismo: recompensas extrínsecas atrasam o momento em que o jogador percebe que a ação base não é divertida. — Evidência: **fraca** (ensaio de opinião com um exemplo, Tower of Hell, sem dados). — https://rowatcher.com/news/the-core-loop-mistake-killing-most-roblox-games

- **Teste de 10 minutos sem recompensas** — pergunta se um jogador novo jogaria 10 minutos sem XP, desbloqueios ou recompensas. — Mecanismo: isola a diversão da ação base. — Evidência: **fraca** (heurística de autor, não validada). — mesma fonte acima

- **Protótipo cedo para "achar a diversão"** — testar o loop principal antes de sistemas periféricos; sistemas concorrentes dividem a atenção do jogador, que tende a escolher uma atividade e abandonar a outra. — Mecanismo: atenção é finita e se concentra. — Evidência: **média** (palestra de Dan Spaventa, Roblox Connect 2022, relatada por Holly Green; sem dados). — https://www.gamedeveloper.com/design/how-supporting-core-loops-and-early-prototyping-are-key-to-your-game-s-success

- **Cada sistema novo deve melhorar uma parte do loop** — se não melhora, corta-se. — Mecanismo: reduz escopo e atrito. — Evidência: **média** (mesma fonte). — mesma fonte acima

- **Compulsion loop = anticipation → action → reward** — a antecipação do estado desejado (ex.: ter ouro suficiente) é o motor, mais que a recompensa. — Mecanismo: condicionamento operante; a recompensa libera dopamina, e o artigo sustenta que a dopamina é produzida na antecipação. — Evidência: **fraca** (artigo conceitual, sem estudos quantitativos citados). — https://gamedeveloper.com/design/compulsion-loops-dopamine-in-games-and-gamification (Samson, 2017) e https://www.gameanalytics.com/blog/the-compulsion-loop-explained

- **Ratio e intervalo de recompensa** — variáveis de Skinner (quanto por ação, quanto tempo entre recompensas). Recompensas variáveis (razão variável) produzem respostas persistentes em animais e humanos. — Mecanismo: imprevisibilidade mantém o comportamento. — Evidência: **média** para o condicionamento em laboratório (Skinner 1953, citado em Harrigan et al., 2011); **fraca** para a transferência a jogos digitais. — https://www.gameanalytics.com/blog/the-compulsion-loop-explained e https://uwaterloo.ca/reasoning-decision-making-lab/sites/default/files/uploads/files/HarDixMacCol_2011.pdf

- **Progressão precisa de uma narrativa de autoria** — o jogador precisa sentir que o caminho é escolha dele. Itens visíveis (cosméticos, títulos) e feedback claro das escolhas ajudam; um caminho linear único e só números tendem a parecer tarefa. — Mecanismo: autonomia (teoria da autodeterminação, citada sem estudos). — Evidência: **fraca** (opinião; exemplos Vampire Survivors e Adopt Me! são ilustrativos). — https://rowatcher.com/news/progression-systems-that-feel-like-chores-share-one-flaw

- **Loop de progressão com metas em três prazos** — metas de curto, médio e longo prazo para estilos diferentes; não bloquear o divertido: o novo jogador deve ter conteúdo na primeira sessão e saber o próximo objetivo. — Mecanismo: conforta com progresso visível sem esconder a ação. — Evidência: **média** (guia de boas práticas). — https://create.roblox.com/docs/en-us/get-started/strategies

- **Métricas de retenção antes do desenvolvimento** — definir KPIs antes; acompanhar D1, depois D7 e D30. — Mecanismo: detecta cedo se o loop não segura. — Evidência: **média** (prática de indústria; sem números de referência nas fontes). — mesma fonte acima

- **Upgrade que aumenta o custo do próximo** (incremental) — cada melhoria em "torneiras" (faucets) também encarece a próxima, então os sinks crescem junto. — Mecanismo: mantém a moeda com valor ao longo do tempo. — Evidência: **média** (raciocínio econômico; o artigo admite que não foi testado com dados). — https://machinations.io/articles/what-is-game-economy-inflation-how-to-foresee-it-and-how-to-overcome-it-in-your-game-design

## Estruturas por gênero (com exemplos)

Os exemplos abaixo vêm das fontes lidas; não há números de retenção ou receita verificados.

- **Simulador (coleta → gasto → multiplicador)** — ação repetível gera moeda; a moeda compra upgrades que aumentam a taxa de ganho; sobe-se de tier. Costuma ter prestígio/rebirth para reiniciar e subir o teto. — Fonte: resumo de guias de tycoon/simulador (third-party, sem dados) em https://www.creation.dev/templates/simulator-template e ver tópico de rebirth em https://devforum.roblox.com/t/virtual-economy-balancing-how-to-do-effectively/466498 (não aberto no detalhe).

- **Tycoon** — mesmo padrão, com construção de estrutura que gera renda; a crítica comum é que o loop vira "esperar e comprar". Fonte: resumo de guias (fraca).

- **Loop de ação base + progressão extrínseca (RPG/aventura)** — exemplo oficial: explorar → lutar → evoluir; a árvore de upgrades é o motor. — https://create.roblox.com/docs/production/game-design/core-loops

- **Obby/ação pura** — Tower of Hell, sem XP por boa parte da vida, com loop de tentar → falhar → repetir → terminar. Exemplo citado por RoWatcher; não verificado por dados. — https://rowatcher.com/news/the-core-loop-mistake-killing-most-roblox-games

- **Coleção/social (Adopt Me!)** — trocas e coleta com escolhas que diferem entre jogadores no mesmo nível. Citado como exemplo positivo por autoria; sem dados. — https://rowatcher.com/news/progression-systems-that-feel-like-chores-share-one-flaw

- **Incremental/idle com sinks de escala** — modelo de Machinations para incremental: custo do próximo upgrade cresce com a produção. — https://machinations.io/articles/what-is-game-economy-inflation-how-to-foresee-it-and-how-to-overcome-it-in-your-game-design

- **Eventos com tempo limitado e recompensa rara** — urgência e valor social; recomendado em guia de Roblox (sem dados). — https://create.roblox.com/docs/en-us/get-started/strategies

## Economia simples (faucets e sinks)

- Inflação ocorre quando entra mais moeda do que sai. Torneiras (faucets) são fontes; ralos (sinks) são remoções. — Machinations (fonte comercial, mas definição consistente com outros). — https://machinations.io/articles/what-is-game-economy-inflation-how-to-foresee-it-and-how-to-overcome-it-in-your-game-design
- Ponto de equilíbrio: torneiras suficientes para manter os ralos significativos, sem sobra. Monitorar a taxa de geração vs consumo e a eficiência de farm conforme o jogo envelhece.
- Ralos comuns: upgrades com custo crescente, itens caros de longo prazo, cosméticos, taxas pequenas em trocas, reset (prestígio). Ressalva: ralos que dão vantagem viram pay-to-win.
- Recomendação prática: modelar o fluxo antes do lançamento (planilha ou Machinations) e segmentar por tipo de jogador (novo vs veterano), porque as taxas de inflação diferem.
- Fonte de exemplo numérico: coal hipotético (pá 1/min, broca 2/min por 100 de moeda, dinamite 3/min por 500) — ilustrativo, não é dado. https://machinations.io/articles/what-is-game-economy-inflation-how-to-foresee-it-and-how-to-overcome-it-in-your-game-design

## O que evitar

- **Grind vazio** — XP e drops "disfarçados de progresso significativo": a versão mais difícil do mesmo desafio, sem mudança de gameplay. Fonte: https://www.wayline.io/blog/endless-grind-progression-loops-ruining-games (opinião, sem dados).
- **Recompensa substituindo o jogo** — a recompensa vira o motivo para jogar, e a sessão vira obrigação (daily, medo de ficar para trás). Mesma fonte acima.
- **Gating que cria atrito artificial** — para forçar compra ou tempo de espera. Mencionado no Roblox por RoWatcher como efeito de algoritmo de descoberta (opinião).
- **Login por recompensa em vez de jogar** — jogador aprende que logar paga mais do que jogar. Mesma fonte RoWatcher (opinião).
- **Recompensa extrínseca erodindo a motivação** — efeito de justificação excessiva: achievements podem reduzir a motivação intrínseca, e o efeito é difícil de reverter. Fonte: Samson (2017), argumento teórico, sem estudo citado.
- **Inflação não planejada** — moeda sem ralo vira sem valor; ex.: NPCs que trocam loot por dinheiro novo em economias de jogadores. Fonte: DevForum (thread de economia de jogadores, trecho).
- **Vício em loot boxes / razão variável** — evidência de associação em surveys, não de causalidade (ver divergências).

## Divergências entre fontes

- **Core loop vs compulsion loop** — Roblox trata o motor de progressão como parte do core loop. GameAnalytics e Samson separam: core loop é o fluxo primário; compulsion loop é o desenho intencional de hábito (antecipação + ação + recompensa). Há divergência de termo; o GameAnalytics admite confusão na indústria.
- **Progressão cria ou não retenção?** — Roblox docs: o motor é essencial (sem ele, o jogo é raso). RoWatcher: progressão não cria retenção, só adia o momento em que o jogador percebe que a ação é fraca. Não é contradição total: a documentação fala de necessidade, RoWatcher de suficiência. Ambos sem dados.
- **Recompensa variável: mecanismo ou só correlação?** — Skinner (1953) e Harrigan et al. (2011) sustentam o condicionamento em laboratório. Dados de loot boxes são secundários e citam associação (Zendle et al., não verificado diretamente). Não há evidência de que o efeito seja igual em jogos digitais.
- **Reset/prestígio** — Machinations diz que reset é "controverso" (opinião). Guias de tycoon/simulador usam rebirth como padrão. Não há dado comparativo.

## Fontes lidas (URLs com 1 linha cada)

1. https://create.roblox.com/docs/production/game-design/core-loops — definição oficial de core loop em três partes e a exigência de um motor de progressão.
2. https://www.gameanalytics.com/blog/the-compulsion-loop-explained — definição de compulsion loop por antecipação, ação e recompensa, com base em operant conditioning.
3. https://gamedeveloper.com/design/compulsion-loops-dopamine-in-games-and-gamification — Samson (2017) sobre dopamina na antecipação, motivação intrínseca e riscos de recompensa extrínseca.
4. https://www.gamedeveloper.com/design/how-supporting-core-loops-and-early-prototyping-are-key-to-your-game-s-success — Holly Green, prototipação e core loop, com base em palestra de Dan Spaventa (Roblox Connect 2022).
5. https://www.wayline.io/blog/endless-grind-progression-loops-ruining-games — crítica ao grind e à progressão que substitui o jogo (opinião).
6. https://rowatcher.com/news/the-core-loop-mistake-killing-most-roblox-games — argumento de que progressão não cria retenção sem loop bom (opinião, sem dados).
7. https://rowatcher.com/news/progression-systems-that-feel-like-chores-share-one-flaw — progressão sem autoria pessoal parece tarefa (opinião).
8. https://machinations.io/articles/what-is-game-economy-inflation-how-to-foresee-it-and-how-to-overcome-it-in-your-game-design — faucets, sinks, inflação e soluções (fonte comercial).
9. https://create.roblox.com/docs/en-us/get-started/strategies — recomendações de progressão, KPIs D1/D7/D30 e cadência de atualizações.
10. https://uwaterloo.ca/reasoning-decision-making-lab/sites/default/files/uploads/files/HarDixMacCol_2011.pdf — citação de Skinner (1953) sobre slot machines e razão variável (não lido na íntegra; resumo via busca).

Observação: não foi possível abrir o artigo da Deconstructor of Fun sobre Destiny (redirecionou para a home do blog) nem o DevForum "How to design the ideal in-game economy" (conteúdo vazio). Por isso não entraram nas notas. Afirmações sobre "2-4x" de retenção de um loop satisfatório em 5 minutos foram descartadas por falta de fonte verificável.
