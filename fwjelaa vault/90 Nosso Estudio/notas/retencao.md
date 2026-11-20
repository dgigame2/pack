# Retenção — notas de pesquisa

Pesquisa feita em 2026-11-19. Foram lidas 8 fontes completas (lista no fim). Não consegui ler palestras GDC com texto nem artigos da Game Developer; a lacuna está em "Divergências".

## Técnicas

- **Definição oficial de D1/D7/D30** — D1 = voltou no dia seguinte à primeira visita; D7 = 8º dia; D30 = 31º dia; cada coorte começa na data da primeira sessão — dado de métrica, não de efeito — evidência forte (é definição) — https://create.roblox.com/docs/production/analytics/retention
- **Entrar na diversão rápido (FTUE)** — o jogador que não chega ao "momento divertido" logo abandona, então o D1 cai — recomendação oficial de chegar ao divertido "idealmente em 5 minutos ou menos"; sem número de efeito — evidência média (recomendação oficial, sem dado) — https://create.roblox.com/docs/production/analytics/retention
- **Tutorial curto e contextual** — tooltips e pop-ups quando o jogador encontra algo novo, em vez de tutorial longo; reduz atrito antes do core loop — recomendação oficial sem dado — evidência média — https://create.roblox.com/docs/production/analytics/retention ; https://create.roblox.com/docs/production/analytics/engagement
- **"Momento de alegria" após o primeiro ciclo do core loop** — recompensa clara logo depois da primeira conclusão do loop, com feedback, moeda ou item — recomendação oficial — evidência média — https://create.roblox.com/docs/production/analytics/retention
- **Recursos iniciais (starter items/moeda)** — dá acesso ao core loop mais cedo, para o jogador ter diversão já na primeira sessão — recomendação oficial — evidência média — https://create.roblox.com/docs/production/analytics/engagement
- **Metas curtas + longas** — meta de curto prazo dá feedback imediato; meta de longo prazo dá direção; ambas sustentam o D7 — recomendação oficial — evidência média — https://create.roblox.com/docs/production/analytics/retention
- **Progressão calibrada** — progressão rápida demais deixa sem conteúdo; lenta demais causa tédio. Oficial recomenda medir a distribuição de jogadores por nível — evidência média — https://create.roblox.com/docs/production/analytics/retention
- **Cadência de conteúdo** — pequenas atualizações a cada 2–4 semanas e grandes a cada 2–3 meses, para sustentar D30 — recomendação oficial sem dado de efeito — evidência média (cadência é opinião de plataforma) — https://create.roblox.com/docs/production/analytics/retention
- **Recursos sociais (grupos, trocas, líderboards)** — motivo para voltar entre atualizações; reforça o sinal de co-play — evidência média — https://create.roblox.com/docs/production/analytics/retention
- **Retenção sob o algoritmo de Home (2026)** — o Roblox passou a medir D1, D2–7 e D8–28 (janela de 28 dias, antes 7) com sinais de play through rate, first play bounce rate, play days e playtime por usuário, e co-play; o objetivo declarado é valorizar jogos que retêm, não só cliques de thumbnail — mecanismo: o algoritmo recompensa quem fica, não quem clica — evidência média (é a política oficial, mas o Roblox não publicou o efeito quantificado; o artigo diz só que DAU "aumentou" sem números) — https://devforum.roblox.com/t/recommended-for-you-algorithm-improvements-that-better-value-long-term-retention/4684575 ; https://about.roblox.com/newsroom/2026/06/optimizing-discovery-great-games-reach-millions-players-roblox
- **Primeiro minuto e bounce** — "first play bounce rate" (saída em sessão curta, 0–60 s e 61–180 s) é sinal negativo; a primeira impressão pesa no algoritmo — documentação oficial — evidência forte para a regra (está na política), média para o efeito na retenção — https://create.roblox.com/docs/discovery
- **Co-play intencional** — jogador que volta com amigos (convite, join, servidor privado) conta como sinal; é secundário — evidência média — https://create.roblox.com/docs/discovery ; https://create.roblox.com/docs/en-us/discovery-faq
- **Média por usuário, não total** — os sinais são médias por usuário, então jogo pequeno com jogadores engajados não é prejudicado pelo volume — documentação oficial — evidência forte para a regra — https://create.roblox.com/docs/discovery
- **Miniatura e título fiéis ao jogo** — thumbnail padrão torna o jogo inelegível para Home; visual quase idêntico a outros reduz descoberta — documentação oficial — evidência forte para a regra — https://create.roblox.com/docs/discovery ; https://create.roblox.com/docs/en-us/discovery-faq
- **Diagnóstico por janela** — se D2–7 e D8–28 caem enquanto D1 se mantém, o problema é a retenção depois do primeiro dia (não o onboarding) — orientação oficial — evidência média — https://create.roblox.com/docs/discovery

## Benchmarks e números (com fonte)

Roblox oficial não publica benchmarks numéricos de D1/D7/D30 (a página de retenção não traz percentuais). Os números abaixo são de terceiros.

- **Mobile, todos os gêneros (GameAnalytics 2025, 16.262 jogos com ≥1.000 MAU):** D1 mediana ~22%; D7 mediana ~4% (just under); D30 mediana ~0,7% — evidência média (amostra grande, mas não é Roblox e não é F2P específico) — https://gamedevreports.substack.com/p/gameanalytics-mobile-and-pc-game
- **Mobile, top 25%:** D1 ~30%+; D7 6–7%; D30 ~1,6–1,8%. **Top 10%:** D1 ~40%; D7 11–12%. **Top 1%:** D1 64–68%; D7 >25%; D30 13–15% — mesma fonte.
- **PC (3.582 jogos com ≥100 MAU):** D1 top 25% 15–16%; D7 top 10% ~10%; D30 top 10% ~2,5% — mesma fonte. PC não separa Steam nem F2P.
- **Ruído e comparabilidade:** o artigo é patrocinado pela PWN Games; os dados são da GameAnalytics. Sinal fraco para decisões finas.
- **Roblox não divulga benchmark de D1 para o próprio ecossistema.** A página de analytics só diz para focar em D1 e tempo médio de sessão primeiro — https://create.roblox.com/docs/en-us/production/analytics (busca), https://create.roblox.com/docs/production/analytics/engagement

## O que evitar

- **Recompensa diária que pune ausência** — um login que, se você não voltar, reseta a recompensa, é descrito como dark pattern temporal. Há um estudo de 1.496 jogos mobile (junho de 2024) que classifica "Daily Rewards" como padrão temporal — evidência forte para a prevalência (89% dos jogos tinham ao menos um padrão), fraca para o efeito na retenção, que o estudo não mede — https://arxiv.org/html/2412.05039v1
- **Padrões de monetização agressivos** — no mesmo estudo, jogos classificados como "dark" tinham mais padrões monetários (média 31,2 vs 4,3 nos saudáveis), e 96,8% deles eram F2P. Associação, não causalidade — https://arxiv.org/html/2412.05039v1
- **Tutorial longo e bloqueante** — o próprio Roblox recomenda o oposto: tooltips e instruções curtas no contexto — https://create.roblox.com/docs/production/analytics/retention
- **Crash e lentidão em aparelho fraco** — com bounce rate como sinal negativo, um jogo que trava no join piora o algoritmo; a comunidade levantou isso no DevForum (opinião de usuários, sem resposta oficial) — https://devforum.roblox.com/t/recommended-for-you-algorithm-improvements-that-better-value-long-term-retention/4684575
- **Otimizar thumbnail chamativa sem conteúdo** — o próprio Roblox diz que o algoritmo de 7 dias premiava isso e que a mudança para 28 dias existe justamente por isso — https://about.roblox.com/newsroom/2026/06/optimizing-discovery-great-games-reach-millions-players-roblox
- **Forçar co-play** — é sinal secundário; a documentação não sugere premiar convite forçado — evidência fraca de que mais co-play gera retenção; é um sinal medido, não um objetivo — https://create.roblox.com/docs/en-us/discovery-faq

## Divergências entre fontes

- **Novos jogos e a janela de 28 dias:** o FAQ oficial diz que "sinais iniciais entram imediatamente" e que novos jogos não esperam 28 dias. O post do DevForum não dá prazo e usuários perguntaram sem resposta. Vale testar com cautela.
- **"First play bounce" — definição:** o doc oficial fala em "short play session" com faixas de 0–60 s e 61–180 s; um resumo em vídeo (third-party) dizia "60 segundos". A versão oficial prevalece.
- **D7 do mercado:** uma fonte dá D7 mediano de ~8% em 2024; a de 2026 dá ~4% (2025). Pode ser diferença de amostra ou erro de uma das duas; não resolvi.
- **D30 top 10%:** um resumo dava ~2,5%, outro ~4%. A leitura mais detalhada atribui 2,5% ao PC; o top 10% mobile não tem número no artigo. Provavelmente confusão entre plataformas.
- **Thresholds de D7 "bons" (15–20%)** circulam em blogs; não há fonte oficial. Não usar como meta.
- **Daily rewards:** o Deconstructor of Fun (apenas snippet, não lido) analisa recompensas diárias como motor de hábito; críticos e o estudo acadêmico as tratam como possível dark pattern. A divisão é entre "dá prazer/motivação" e "existe para reter e cobrar"; não há dado que resolva.
- **Gap:** não li palestras GDC com texto nem artigos de Game Developer/Gamasutra; o material de design vem quase todo da documentação oficial Roblox. Evidência de design fora do Roblox continua fraca.

## Fontes lidas

- https://create.roblox.com/docs/production/analytics/retention — definições de D1/D7/D30 e recomendações de onboarding, progressão e end-game (oficial)
- https://create.roblox.com/docs/production/analytics/engagement — tempo de sessão, primeiros 5 min, tutoriais curtos, recursos iniciais (oficial)
- https://create.roblox.com/docs/discovery — sinais de Recommended For You, janelas D1/D2–7/D8–28, bounce rate, diagnóstico (oficial)
- https://create.roblox.com/docs/en-us/discovery-faq — novos jogos, thumbnails, benchmarks não afetam ranking, pesos e número de jogos pré-selecionados (oficial)
- https://devforum.roblox.com/t/recommended-for-you-algorithm-improvements-that-better-value-long-term-retention/4684575 — anúncio de 15/06/2026 e reações da comunidade (lido via versão .json; oficial + não oficial)
- https://about.roblox.com/newsroom/2026/06/optimizing-discovery-great-games-reach-millions-players-roblox — justificativa da mudança para retenção de longo prazo (oficial)
- https://arxiv.org/html/2412.05039v1 — estudo de 1.496 jogos mobile sobre dark patterns (acadêmico, 2024)
- https://gamedevreports.substack.com/p/gameanalytics-mobile-and-pc-game — benchmarks GameAnalytics 2026 (dados de 2025; patrocinado)
