# O que faz um jogo divertido — notas de pesquisa

Nota de método: consegui ler 9 fontes. Os PDFs originais (MDA de Hunicke/LeBlanc/Zubek, Theory of Fun de Koster, o artigo SDT de 2009 e o keynote de Koster) não puderam ser extraídos, então usei resumos confiáveis (Wikipedia, abstract do artigo SDT, artigos da Game Developer e documentação oficial do Roblox). "Juice it or lose it" aparece nos resultados como palestra de Jonasson e Purho (GDC Europe 2012); não achei palestra de Steve Swink sobre game feel, e não li o livro dele. Tudo que segue sem fonte direta está marcado como não verificado.

## Princípios

1. **Diversão é dominar padrões.** Mecanismo: o cérebro busca padrões, e a graça está em aprender um padrão; quando ele fica transparente, a diversão acaba; ruído que não forma padrão gera frustração. Evidência: **fraca** (teoria de design, resumida por fonte secundária; a ligação com dopamina é analogia do próprio Koster). Fonte: https://gamedeveloper.com/design/raph-koster-s-theory-of-fun-ten-years-on

2. **MDA: mecânicas → dinâmicas → estéticas.** Mecanismo: separa o que você programa (regras, dados) do que acontece em jogo (comportamento emergente) e do que o jogador sente. Use para checar se a emoção pretendida aparece no teste. Evidência: **fraca** (vocabulário conceitual, sem validação experimental). Fonte: https://en.wikipedia.org/wiki/MDA_framework (resume Hunicke, LeBlanc e Zubek, workshop AAAI 2004).

3. **Oito tipos de diversão (LeBlanc).** Sensação, fantasia, narrativa, desafio, companheirismo, descoberta, expressão e submissão; competição aparece como nona no artigo. Mecanismo: serve de checklist — quais desses seu jogo oferece? Evidência: **fraca** (taxonomia, sem dados que a validem). Fonte: https://en.wikipedia.org/wiki/MDA_framework

4. **Flow: desafio na medida da habilidade, metas claras e feedback imediato.** Mecanismo: com desafio no ponto certo, a atenção se fixa e a noção de tempo some; desafio abaixo da habilidade leva a tédio, acima leva a ansiedade. Evidência: **média** (décadas de pesquisa de Csikszentmihalyi, mas medido por autorrelato e com efeito pequeno sobre desempenho). Fonte: https://en.wikipedia.org/wiki/Flow_(psychology)

5. **Autodeterminação: competência, autonomia e relação.** Mecanismo: sentir-se capaz, com escolhas próprias e conectado a outros aumenta prazer e vontade de voltar; controles intuitivos e sensação de presença aparecem ligados às duas primeiras. Evidência: **média** (Ryan, Rigby e Przybylski 2006: quatro estudos, correlacionais, com autorrelato; no estudo 4, cada necessidade previu prazer e jogo futuro sozinha; o abstract não traz tamanhos de efeito). Fonte: https://pure.ewha.ac.kr/en/publications/the-motivational-pull-of-video-games-a-self-determination-theory-/

6. **Retenção começa no loop central e no primeiro contato.** Mecanismo: o Roblox define D1 como o loop central, a introdução (FTUE) e a performance; D7 como progressão; D30 como sistema de fim e conteúdo contínuo. Evidência: **média** (guia oficial da plataforma, mas sem benchmarks numéricos e sem prova causal). Fonte: https://create.roblox.com/docs/en-us/production/analytics/retention.md

7. **Chegar à parte divertida rápido.** Mecanismo: o jogador decide cedo se fica; a introdução deve ensinar fazendo, dar recompensa cedo (XP inicial baixo) e terminar com um "momento de alegria". Evidência: **média** (orientação oficial do Roblox, sem números). Fonte: https://create.roblox.com/docs/production/game-design/onboarding

8. **Juice: pequenas surpresas e deleites no feedback de cada ação.** Mecanismo: reforço imediato e sensorial torna a ação mais satisfatória e conecta-se ao feedback imediato do flow. Evidência: **fraca** (prática de design, sem estudo controlado lido). Fonte: https://roblog.co.uk/2024/03/juicy-games/

## Técnicas práticas

**Game feel e juice (não verificado nas fontes lidas; conhecimento geral de design):**
- Resposta no mesmo frame: efeito visual e sonoro no instante do acerto ou da coleta.
- Tweens curtos (escala, squash e stretch) para dar peso sem atrasar a ação.
- Hit-stop de poucos quadros em impactos fortes, para tornar o golpe legível.
- Números e partículas que mostram a magnitude do resultado.
- Fonte que contém a lista detalhada não foi acessível: https://gamejuice.pages.dev/articles/juice-it-or-lose-it-lessons é página em construção, sem conteúdo.

**Primeiros 60 segundos (fontes: documentação e comunidade Roblox):**
- Mostrar o loop completo na primeira ação, com recompensa visível cedo. Fonte oficial: https://create.roblox.com/docs/production/game-design/onboarding
- Ensinar fazendo, não com caixas de texto. Fonte: comunidade (rowatcher), fraca.
- Carregamento rápido, ponto de spawn claro e UI que funcione no celular: a documentação recomenda testar em vários dispositivos. Fonte oficial: retenção (link acima).
- A janela de "30 a 90 segundos" vem de blogs, não da Roblox; a orientação oficial fala em chegar à diversão em até 5 minutos.

**Playtest e sinais observáveis:**
- Funil de onboarding por etapa: onde o jogador cai (recurso "Player Funnel" do Roblox).
- Testes A/B em passos do tutorial e ajuste de XP e moeda inicial por configuração, sem republicar (recurso "Experiments" e "Configs" do Roblox; fonte oficial de onboarding).
- Retenção por coorte de primeiro acesso em D1, D7 e D30.
- Sugestão própria (não verificada em fonte): observar sem ajudar, anotar onde o jogador trava, e perguntar ao final "o que você faria agora?". Um fornecedor de ferramentas afirma que desenvolvedores são maus juízes da própria introdução; trate como opinião comercial.

## Críticas e divergências

- **Koster reduz diversão a aprendizado de padrões.** Críticos acham a visão mecânica demais. Arte, narrativa e jogos sem objetivo claro ficam mal explicados, e a "ludonarrativa" (Hocking, citado no artigo) mostra desencontros entre regra e história. O próprio Koster admite que meditação, conforto e narrativa são formas válidas de brincar fora da teoria.
- **MDA** é criticado por ter lista de emoções arbitrária e foco em mecânicas, o que o torna pouco útil para gamificação e jogos de experiência.
- **Flow** é medido com autorrelato depois do fato; o modelo de canais não garante o equilíbrio desafio-habilidade; o efeito sobre desempenho é pequeno; Csikszentmihalyi alertou que atividades com flow podem viciar; críticos dizem que gamificação transforma flow em trabalho não pago.
- **SDT** em jogos: evidência correlacional, autorrelato, poucos jogos por estudo. Não encontrei estudos específicos sobre jogos de Roblox, público jovem ou celular; a aplicação a esse contexto é inferência.
- **Juice:** Folmer Kelly (palestra "Don't Juice It or Lose It", GDC Europe) argumenta que polimento pode custar imersão e que o contexto do jogo deve vir antes. Equilíbrio: juice sem contexto pode enganar sobre a qualidade real.
- **Roblox:** a documentação oficial dá orientações, não números; os números de tempo (30, 60, 90 segundos) são de terceiros e conflitam entre si.

## Fontes lidas

- https://en.wikipedia.org/wiki/MDA_framework — resumo do MDA e da taxonomia de LeBlanc, com críticas.
- https://gamedeveloper.com/design/raph-koster-s-theory-of-fun-ten-years-on — Koster sobre aprendizado, dopamina e limites da teoria (secundária).
- https://en.wikipedia.org/wiki/Flow_(psychology) — condições, características e críticas do flow (artigo com tags de qualidade).
- https://pure.ewha.ac.kr/en/publications/the-motivational-pull-of-video-games-a-self-determination-theory-/ — abstract do artigo SDT de 2006 com os quatro estudos.
- https://create.roblox.com/docs/production/game-design/onboarding — orientação oficial de FTUE.
- https://create.roblox.com/docs/en-us/production/analytics/retention.md — definições de D1, D7, D30 e alavancas.
- https://gamedeveloper.com/design/video-indies-resist-the-urge-to-juice-it-or-lose-it- — crítica de Folmer Kelly ao juice.
- https://roblog.co.uk/2024/03/juicy-games/ — resumo de juice, com pouca técnica concreta.
- https://gamejuice.pages.dev/articles/juice-it-or-lose-it-lessons — tentativa sem conteúdo (página em construção).

Tentadas sem extração (PDF binário): https://users.cs.northwestern.edu/%7Ehunicke/MDA.pdf, https://www.raphkoster.com/gaming/atof/theoryoffun.pdf, https://selfdeterminationtheory.org/wp-content/uploads/2014/04/2009_PrzbylskiRyanRigby_PSPB-1.pdf, https://www.raphkoster.com/wp-content/uploads/2026/07/Austin-Game-Conference-2003-Keynote-Theory-of-Fun.pdf.
