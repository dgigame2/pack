# Estudo: 20 vídeos sobre desenvolvimento e design de jogos no Roblox
Data: 18/11/2026 · Transcrições em `transcricoes/` · Método: os 7 passos do documento de brainstorm (princípio, mecanismo, evidência, aplicação, riscos, alternativas, prioridade), com postura crítica.

---

## 0. Antes de tudo: quanto confiar em cada fonte

| Fonte | Evidência | Conflito de interesse |
|---|---|---|
| Roblox Creators — "Recommended for You" | **Alta** (oficial) | É a própria plataforma |
| RDC 2025 — Analytics e experimentos (Brookhaven, Adopt Me, TDS) | **Alta** (dados de estúdios grandes) | Vende a ferramenta de A/B test |
| rasdev (3 vídeos de algoritmo) | Média (cita documentos do Roblox + dados próprios) | **Vende site de tendências** (rblx/Reblocks) |
| MoseyTube77 — mudanças do algoritmo | Média (cita posts do Roblox) | Vende "academia" |
| Tizzy RBLX (3 vídeos) | Média-alta (mostra dashboard real, US$ 119k/mês) | Discord de talentos; viés de sobrevivente |
| Zyonic (2 vídeos) | Média (mostra números) | Patrocinado (Meshy, Forge); já tinha público do jogo anterior |
| Tap — jogo de 100 CCU com 2M Robux | Média (mostra números) | Discord próprio |
| bubDEV — anúncios | Média-baixa | **Vende templates** |
| janisjanis01 — RNG em 30 dias | Média (mostra prejuízo real) | Patrocinado (Meshy) |
| Dumble — 28 dicas de IA | Baixa-média (dicas práticas) | Patrocinado (Forge) |
| tef — "jogo viral com IA" | **Baixa** (o jogo teve 241 visitas no 1º dia) | Patrocinado (Forge) |
| AlvinBlox, SmartyRBX, waveshine | Baixa-média (opinião; vídeos de 1–2 anos, **antes das mudanças de 2026**) | Cursos/canal |
| Aphazune | Baixa (ensaio de opinião) | — |

**Leitura crítica geral:** quase todo mundo mostra o jogo que deu certo. Os fracassos que apareceram de passagem são os dados mais honestos do conjunto:
- Tizzy: 4 fracassos antes do sucesso (clone de US$ 4 mil, template de US$ 600, jogo de US$ 12 mil sem lucro, clone de tendência feito com IA).
- janis: 2 devs experientes, 30 dias de trabalho, **−170 mil Robux** de prejuízo, ~20 CCU (depois 100).
- tef: "jogo viral com IA" em 3 dias, 241 visitas no primeiro dia.
- Tap: clone "Steal a Fossil" com anúncio rodando e 0 CCU.

---

## 1. Como o algoritmo funciona agora (o que mudou em 2026)

**1.1 Duas etapas (oficial).** Primeiro o Roblox seleciona milhares de jogos usando sinais de *todas* as fontes (anúncios, busca, amigos, destaque). Depois ordena para cada jogador usando **só os sinais de quem achou o jogo organicamente na Home**.
- *Mecanismo:* o Roblox quer prever se um jogador "frio" vai gostar. Jogador de anúncio ou de amigo não representa isso.
- *Aplicação:* anúncio serve para **entrar no teste**, não para subir no ranking.

**1.2 Sinais medidos, por jogador e não no total** (rasdev e Mosey citando o Roblox): taxa de play (clique → jogar), rejeição no primeiro acesso (<60 s e 1–3 min), dias jogados, tempo de jogo (rasdev: acima de ~60 min por jogador quase não conta mais), sessões qualificadas, **dias de co-play intencional**, dias com gasto, Robux por usuário.
- Por ser "por jogador", jogo pequeno compete de igual com jogo grande.

**1.3 Janela de 28 dias (desde junho/2026).** Antes o peso maior era a primeira semana. Agora conta D1, D2–7 e **D8–28** separadamente.
- ⚠️ **Contradiz diretamente "surfar picos"**: jogo que explode e morre é mais penalizado que antes.
- Contraponto (rasdev): metade dos jogos com mais de 10 mil CCU médio tem menos de 3 meses. Tendência continua funcionando, mas quem tem motivo para voltar dura mais.
- *Aplicação:* **planejar a atualização da semana 2 antes de lançar.**

**1.4 Trava de idade — talvez o ponto mais importante para vocês.** Jogadores com menos de 16 anos só veem jogos que tenham N **jogadores altamente engajados** em 60 dias. Eram 500, depois 250, e **a partir de novembro/2026 são 100**. A alternativa é pagar uma revisão acelerada: Mosey fala em 50 mil Robux reembolsáveis, e janis pagou 100 mil numa época anterior.
- Jogador altamente engajado = conta mais antiga, que jogou um pouco o seu jogo e gastou Robux em *algum lugar* do Roblox recentemente.
- Caso real: janis gastou 13 mil Robux em anúncio e chegou a só **35** desses jogadores.
- Tap: jogos novos ficam como 16+ até passar da trava. Lançar um jogo infantil sem orçamento significa mostrá-lo só para quem tem 16+, que não quer jogar aquilo.
- ⚠️ **Jogos de tendência quase sempre miram em crianças.** Sem orçamento para passar dessa trava, surfar tendência infantil fica muito mais difícil.

**1.5 Vídeo de gameplay na página do jogo.** Toca sozinho no bloco "Recomendado para você" e na aba Moments.
- Roblox (resultado inicial): +31% a +39% de tempo de jogo vindo de recomendações.
- Tap (relato): sem vídeo, ~2,5% dos cliques viravam partidas; com vídeo, 50–80%.
- Regras: gameplay real, sem narração, sem música com letra, nada que não esteja no jogo.
- **É grátis e leva uns 20 minutos para gravar. Prioridade máxima.**

**1.6 Thumbnail e ícone são uma promessa.** A taxa de play foi separada da taxa de rejeição justamente para punir clickbait.
- Adopt Me: a thumbnail é vista por **jogadores novos**, então precisa mostrar a fantasia central, não a novidade da atualização. A melhor dela ("coleção de pets") rende 1,7× a média.
- TDS: estilo desenhado à mão rendeu 2× mais cliques que um render 3D cheio de ação.
- Tap: CTR médio de anúncio é 1–2%; bom é 4–7%. Ele gera ~100 thumbnails com IA e roda as 10 melhores.
- Imagem 16:9 virou importante (busca e anúncios: +40% de partidas, segundo rasdev).

**1.7 Anúncios: o que todos dizem na prática.**
- Servem para dar a "faísca" e gerar dados. Jogador de anúncio é de baixa qualidade (sai rápido, não compra, dá deslike).
- Configuração comum: orçamento total, 5–7 dias, metas padrão. Valor pequeno por mais tempo funciona melhor que tudo de uma vez.
- Zyonic e bubDEV: depois que o jogo segura ~40 CCU sem anúncio, **desligar o anúncio fez as métricas e as recomendações subirem**.
- bubDEV: se depois de ~14 dias o jogo não pegou no algoritmo, provavelmente não vai pegar.
- Gastos citados: Zyonic ~US$ 370 em 2 semanas; janis 13 mil Robux; Mosey ~US$ 10/dia.

**1.8 Busca como faísca grátis** (bubDEV, evidência média-baixa). Jogos com nome que bate numa busca em alta (ex.: "steal brain rot", "don't wait") entraram no algoritmo **sem anúncio nenhum**, com poucos milhares de impressões vindas da busca.
- Para surfar tendência sem dinheiro, **é a hipótese mais barata de testar.**

**1.9 Cópias.** O roadmap do Roblox inclui remover cópias de título e thumbnail, e rasdev diz que as cópias acabam morrendo. Tap mostra centenas de "Throw Food For X" com **a mesma thumbnail**.

**1.10 Mercado.** Adultos são o grupo que mais cresce. Nos EUA, 18+ gastam pelo menos 50% mais (dado do Roblox citado por rasdev). Mais de 70% dos 100 maiores jogos rodam anúncio.

---

## 2. Design: o que se repete entre os vídeos

**2.1 Blocos de construção (Tizzy, o melhor framework do conjunto).** Todo jogo de sucesso do mesmo nicho é "o mesmo jogo por baixo". O que muda são alguns blocos:
`fantasia (verbo principal)` · `mecânica única` · `loop central` · `onde fica o RNG (antes/depois de pegar)` · `design de nível` · `tensão (PvE/PvP, pressão de tempo, ciclo tensão→alívio)` · `progressão (mais rápido / mais forte)` · `coleção`
- Regra dele: pegar um jogo de referência e **mudar ~20%** (fantasia e mecânica única) dá 1–10 mil CCU. Para 100 mil CCU, são precisos uns 40% de mudanças significativas.
- Exemplo: Steal an Egg = loop de Escape Tsunami + reposição de estoque a cada 5 min do Grow a Garden + PvP na fuga.
- **É a versão operacional do "roube o motivo, não o jogo"** do seu documento.

**2.2 Tema novo + loop familiar (Zyonic).** O jogador entra pelo tema e fica porque já entende o jogo. "Ser único ajuda, ser único demais mata." Para achar lacunas: App Store, Steam, temas que ainda não existem no Roblox.

**2.3 Teste da ideia (AlvinBlox, Tizzy, Dumble):**
- Dá para explicar em uma frase?
- Dá para entender sem ler nada? ("E se o jogo estivesse em chinês?")
- É divertido nos primeiros 10 segundos?
- Uma mecânica simples com profundidade (rejogabilidade)?
- Gancho de curiosidade para amanhã?
- **Ostentação social** (mostrar o que conseguiu)?
- **Momentos "clipáveis"**? YouTuber grava isso de graça (ex.: o ladrão vira ragdoll e é arremessado no vazio).

**2.4 Primeiro minuto.**
- Entrar e já estar jogando (Hustle Valley: em 1 segundo você está correndo).
- Tutorial é "mostre, não fale" e tem que ser medido em funil.
- Zyonic adicionou um tutorial que **reduziu a sessão em 2 minutos** e só percebeu 2 semanas depois.
- Tizzy: uma cutscene de entrada baixou a rejeição de 22% para 15–16%.

**2.5 Sensação (juice).** Toda ação precisa de som, tremida de câmera e um número aparecendo. Tempo de jogo baixo quase sempre significa core loop sem satisfação (Tizzy).

**2.6 Retenção** (agora mais importante por causa da janela de 28 dias):
- Algo acontece enquanto você está fora (Grow a Garden).
- Progresso salvo (perder progresso é o jeito mais rápido de perder o jogador).
- Roleta com cooldown de 1 hora; 3 desafios diários sorteados entre 10.
- Atualização semanal; admin abuse e eventos.
- Servidores separados por nível, para veterano não espantar iniciante.

**2.7 Co-play.** Bônus por jogar com amigo, botão de convidar ("friend boost": um convida o outro, e o ciclo continua). Agora tem chat de amigos que acompanha o grupo entre jogos.

**2.8 Monetização:**
- Starter pack barato.
- **Produto consumível em momento de contexto**: "dobrar ganhos offline por 19 Robux" aumentou muito a conversão (Tizzy).
- Três faixas de preço: pequeno, médio e grande (as "batatas fritas").
- Upsell no contexto (RDC/Brookhaven): +10% de receita por usuário e +18% de conversão, **sem perder retenção**.
- Mostrar as probabilidades em item aleatório pago (é regra do Roblox).
- ⚠️ Contradição: rasdev diz para evitar pay-to-win. Tap diz para fazer passes "essenciais", que obrigam a comprar para progredir. Os dois funcionam no curto prazo. O segundo cobra o preço na retenção e na reputação.

---

## 3. Processo: como os que deram certo trabalham

1. **Lançar pequeno e rápido. Não polir antes de alguém jogar** (rasdev, Zyonic). "Se não gostarem, abandone."
2. **Volume de tentativas.** Com IA, a primeira versão leva um fim de semana. Quem lança mais tem mais chances (rasdev).
3. **Iterar todo dia.** Build a Base and Steal teve **9 tutoriais diferentes**, patches diários e atualização grande toda semana. Hack a Business foi de 0 a 1 mil CCU em 2 semanas assim.
4. **Hipótese com 3 evidências** (Tizzy): feedback dos jogadores + o que o maior concorrente faz + métrica, como o ponto em que os novos jogadores saem no gráfico de retenção da primeira sessão. Depois lançar, medir e reverter se não funcionar.
5. **Observar alguém jogando sem ajudar.** Cada vez que você precisa explicar algo, isso é algo para consertar.
6. **Jogar no celular e no console.** ~30% dos jogadores de Build a Base and Steal são de console. Melhorar o onboarding no console subiu o D1.
7. **A/B test exige volume e ~2 semanas** (RDC). Não decidir no dia seguinte (efeito novidade). Para jogo pequeno, o que funciona é o **teste de thumbnails nativo do Roblox**. A/B de mecânica é coisa de jogo grande.

**Fluxo com IA (Dumble):**
- Prompt específico (onde, tamanho, referência visual).
- Uma feature por vez; colar o erro em vermelho do Output, não só "quebrou".
- Pedir para a IA testar no Studio.
- Arquivo de memória do projeto e **um script de config com todos os números** (para ajustar o balanceamento sem gastar prompt).
- Testar na visualização de celular; usar o histórico de versões antes de mudanças grandes.

---

## 4. Contradições entre os vídeos (e como eu as leio)

| Tema | Lado A | Lado B | Minha leitura |
|---|---|---|---|
| Surfar picos | Metade dos jogos grandes é nova; vá rápido (rasdev) | Janela de 28 dias pune quem morre rápido (Roblox) | Surfar ainda funciona, mas **com um motivo para voltar já no lançamento** |
| Público | O maior público é criança (rasdev, Tizzy) | Sem dinheiro, mire em 16+ (Tap) | Depende do orçamento para passar da trava de 100 jogadores engajados |
| Tutorial | Nada de tutorial (rasdev) | Partida-tutorial imediata (Dumble), funil (Tizzy) | Tutorial **jogável** nos primeiros segundos, medido no funil |
| Anúncio | Precisa de dinheiro (Tap, Zyonic) | A busca pode bastar (bubDEV) | Testar a busca primeiro (grátis) e só usar anúncio com pouco dinheiro |
| Monetização | Sem pay-to-win (rasdev) | Passes "essenciais" (Tap) | Vender **conveniência e aceleração**, não muro de progresso |
| Originalidade | Copie a estrutura, mude 20% (Tizzy) | Cópia morre (rasdev, Tap) | Copiar a **estrutura** funciona; copiar a **thumbnail e o nome** morre |

---

## 5. O que isso muda no plano de vocês (surfar picos, 2 pessoas, tokens do Claude)

**Revisões honestas do que eu disse antes:**
- ⚠️ **"Throw X for Y" já está saturado.** Na análise das paradas eu indiquei esse formato como um bom primeiro jogo. Tap mostra centenas de clones com a mesma thumbnail. Entrar ali com mais um clone é exatamente o erro que ele descreve. Só vale com um diferencial **visível na thumbnail**.
- ⚠️ **O coletor de tendências só vê jogos que já estão nas paradas.** rasdev diz que o jogo que vai explodir daqui a um mês está hoje com uns 200 CCU, e isso ainda não aparece nas paradas. O coletor serve para confirmar ondas, não para pegá-las no começo. A camada da **busca** do Roblox (ver 1.8) pode ajudar nesse ponto.
- ⚠️ **Ragdoll está no pico** (rasdev: de 8 para 79 jogos em 5 semanas). Os dados que coletamos batem com isso. Melhor evitar.

**O que eu priorizaria (em ordem de custo × impacto):**
1. **Decidir o público antes da ideia.** Para jogo infantil, vocês têm orçamento para chegar a 100 jogadores altamente engajados ou para a revisão acelerada? Se não, 16+ ou nichos de público mais velho (o Tap lucrou 1,9M Robux com um pico de 100 CCU).
2. **Método de escolha de ideia (rasdev + Tizzy):** achar algo crescendo esta semana → achar 3 jogos novos com a mesma ideia → aplicar os blocos do Tizzy → mudar a fantasia e a mecânica única (~20%) → checar se o diferencial aparece na thumbnail.
3. **Pacote de lançamento:** vídeo de gameplay na página, 5–10 thumbnails para teste, ícone e nome que batam numa busca em alta, primeiro minuto igual ao que a thumbnail promete.
4. **Retenção mínima já no lançamento:** progresso salvo, uma recompensa diária ou roleta com cooldown, bônus de amigo, e a atualização da semana 2 já planejada.
5. **Monetização mínima no dia 1:** starter pack barato, um produto consumível contextual, passes em 3 faixas de preço.
6. **Prazo:** janis levou 30 dias e foi tarde e caro; tef levou 3 dias e saiu sem foco. O alvo de 1–2 semanas continua certo.
7. **Esperar fracassos.** Todo mundo que deu certo fracassou várias vezes antes. Cada tentativa precisa ser barata.

---

## 6. Resumo de cada vídeo (uma linha)
1. **Roblox — Recommended for You**: seleção por todas as fontes, ordenação só com o tráfego orgânico da Home.
2. **RDC 2025**: feature flags, A/B test (esperar ~2 semanas, segmentar), upsell contextual +10% de receita, thumbnails para jogador novo.
3. **rasdev — New Rules 2026**: janela de 28 dias, rejeição no primeiro acesso, co-play, vídeo no bloco, trava de idade (250→100), anúncio não conta no ranking.
4. **rasdev — New Era**: metade dos jogos grandes é nova; construir ficou barato, se destacar ficou caro; adultos; método de ideia em 3 passos; ragdoll no pico.
5. **rasdev — Most Valuable**: as 8 etapas (ideia → clique → ficar → voltar → gastar → anúncios → dados); limite de 60 min; anúncios incrementais.
6. **MoseyTube77**: 6 mudanças com exemplos (D1 12% → D7 2%); roleta e desafios diários; anúncio a ~US$ 10/dia só para ser testado.
7. **Tizzy — Design para crianças de 5 anos**: os blocos de construção; mudar 20%.
8. **Tizzy — US$ 119k/mês**: o gargalo é talento e execução; UX; jogar no celular e no console; simples com profundidade; clipável; volume de iterações.
9. **Tizzy — Melhorar stats**: cada métrica tem um culpado típico; hipótese com 3 evidências; starter pack e consumível contextual.
10. **Zyonic — Não é sorte**: mecânica achada brincando com física; testes no Discord; anúncio por 2 semanas sem resultado, desligou, e o jogo cresceu para 5–7 mil CCU.
11. **Zyonic — 50M visitas**: tema novo + loop familiar; ~US$ 370 em anúncios; servidores por nível; tutorial que piorou a sessão.
12. **Tap — 100 CCU, 2M Robux**: nicho e público mais velho; incrementais 2D; vídeo na página; 100 thumbnails; passes "essenciais"; Obsidian como memória.
13. **tef — Viral com IA**: contraexemplo (sistemas demais, sem gancho, 241 visitas).
14. **janisjanis01 — RNG em 30 dias**: misturou balão + RNG + tower defense; cutscene em sorteio raro; prejuízo de 170 mil Robux; trava de 16+.
15. **AlvinBlox — Por que jogos explodem**: ideia em 1 frase, intuitiva, diversão imediata, apelo amplo, FOMO (antes de 2026).
16. **bubDEV — Anúncios**: anúncio por 5–7 dias com valores padrão; **busca como faísca grátis**; comunidade externa (vende templates).
17. **Dumble — 28 dicas de IA**: o fluxo prático com Claude (config, memória, uma feature por vez, celular, juice).
18. **SmartyRBX — 99% falham**: inferno de tutoriais, jogo dos sonhos grande demais, disciplina > motivação, terminar algo pequeno.
19. **waveshine — 2,3M Robux em 3 dias**: um "gimmick" de curiosidade (contagem regressiva global); de 2 anos atrás, viés de sobrevivente.
20. **Aphazune — Design não faz sentido**: crítica de opinião; "por que eu jogaria isso?" e respeitar o tempo do jogador.
