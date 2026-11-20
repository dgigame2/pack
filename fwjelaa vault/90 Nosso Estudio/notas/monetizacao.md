# Monetização — notas de pesquisa

Pesquisa feita em 2026-11-19. Números marcados como "resumo de busca" vieram de resultados de busca e não foram confirmados na página lida.

## Técnicas (técnica — mecanismo — evidência [forte/média/fraca] — fonte URL)

- **Game passes (compra única)**: benefício permanente pago uma vez em Robux. Mecanismo: compra única para privilégio contínuo. Evidência: forte (definição oficial). Fonte: https://create.roblox.com/docs/en-us/production/monetization
- **Developer products (compra repetida)**: itens consumíveis, moeda, boosts. Mecanismo: receita recorrente por sessão ou progressão. Evidência: forte (definição oficial); o relatório GameAnalytics cita consumíveis e boosts como tipos usados, mas como recomendação, não como dado medido. Fontes: https://create.roblox.com/docs/en-us/production/monetization ; https://www.gameanalytics.com/cn/reports/2025-roblox-report
- **Assinaturas**: benefício recorrente mensal, enquanto o usuário paga. Regional pricing ativado por padrão e não pode ser desligado (resumo de busca, não verificado na página). Evidência: média. Fonte: https://create.roblox.com/docs/en-us/production/monetization
- **Price optimization (teste A/B de preço)**: a Roblox testa preços diferentes em grupos de usuários e mede conversão. Requisitos: cerca de 60.000 transações nos últimos 30 dias somando todos os produtos; preços hard-coded precisam virar dinâmicos (via MarketplaceService). Duração: cerca de 3 semanas de teste e 4 semanas de revisão; reteste pelo menos a cada 90 dias. Adoção: só se o teste gerar aumento incremental positivo na receita total. Não se aplica a assinaturas. Evidência: forte para o mecanismo (documentação). Fonte: https://create.roblox.com/docs/en-us/production/monetization/price-optimization
- **Price optimization, resultado citado**: mediana de +26% de receita entre países testados (resumo de busca de comunicado da Roblox de abril de 2025; página não lida; a Roblox diz que é resultado inicial). Evidência: média, dado de fonte oficial mas sem método completo. Fonte: https://corp.roblox.com/newsroom/2025/04/roblox-launches-regional-pricing-for-in-experience-items
- **Resultado negativo do teste**: um criador relatou que quase todos os produtos retornaram sem sugestão de mudança; a Roblox confirmou que os preços já estavam bons. Evidência: fraca (um relato). Fonte: https://devforum.roblox.com/t/price-optimization-returned-no-results-after-a-long-period-of-time/4025057
- **Venda de itens aleatórios pagos (caixas/roleta)**: permitida com divulgação de odds e restrição regional. Mecanismo: receita de gacha/roleta com exigência de transparência. Evidência: forte (regra oficial). Fonte: https://create.roblox.com/docs/en-us/production/monetization/paid-random-items
- **Premium Payouts substituído**: o programa Engagement-Based Payouts (Premium Payouts) foi descontinuado em 24/07/2025 e substituído pelo Creator Rewards; o pagamento é proporcional ao tempo de membros Premium no jogo. Evidência: forte para o status, sem fórmula pública. Fonte: https://create.roblox.com/docs/en-us/production/monetization/premium-payouts
- **Retenção antes de monetização**: um guia sugere só adicionar passes depois de D7 acima de 15% (regra de bolso, sem fonte primária). Evidência: fraca. Fonte: https://rolearn.dev/guidance/monetization-fundamentals (resumo de busca)
- **Passes e produtos em proporção**: um guia sugere cerca de 60–70% da monetização em passes e 30–40% em produtos (regra de bolso). Evidência: fraca. Fonte: https://rowatcher.com/news/developer-products-vs-game-passes-you-re-using-both-wrong (resumo de busca)
- **Passes acima de 500 Robux perdem conversão**: relato de um comentarista, sem método. Evidência: fraca. Fonte: relato de resumo de busca de blog de monetização, sem URL primária confiável.
- **Teste de preço com consumível**: começar com um consumível que combine com o gênero e testar 2 ou 3 preços em semanas diferentes, medindo conversão. Evidência: fraca (conselho de blog). Fonte: resumo de busca de comentário de monetização.

## Números oficiais (DevEx, divisão de receita, resultados citados) com fonte e data

- **Taxa DevEx padrão**: US$ 0,0038 por Earned Robux. Vigente desde 05/09/2025, às 10h PT. Equivale a US$ 114 por 30.000 Earned Robux. Fonte: https://create.roblox.com/docs/en-us/production/monetization/developer-exchange (lida; a página diz que a taxa "is subject to change").
- **Taxa DevEx 18+ (EUA)**: 0,0054 por Earned Robux para certos ganhos de jogadores verificados com 18+ em jogos elegíveis. Início: 08/06/2026. Fonte: https://create.roblox.com/docs/en-us/production/monetization/18-plus-devex-rate
- **Anúncio do aumento de 42%**: Roblox anunciou aumento de 42% da taxa para gastos de jogadores dos EUA com 18+ em jogos elegíveis (avatares R15), para passes, assinaturas em Robux, itens selecionados e servidores privados. Abril de 2026. Fonte: https://about.roblox.com/newsroom/2026/04/roblox-fuels-high-fidelity-games-over-18-players-increases-qualifying-devex-rate-42
- **Mínimo para cashout**: 30.000 Earned Robux. Fonte: página de DevEx acima.
- **Pagamento Creator Rewards (antigo Premium Payouts)**: sem valor por Robux público na página lida. Fonte: https://create.roblox.com/docs/en-us/production/monetization/premium-payouts
- **Divisão de receita por venda de passe**: o resumo de busca diz que o criador fica com 70% dos Robux gastos em passes do próprio jogo. A página oficial de monetização lida não traz percentual para passes e produtos; o 70% não foi confirmado. Use a documentação atual antes de citar.
- **Catálogo e Creator Store**: sem percentual na página lida. Plugins e models: preço mínimo de US$ 4,99 e US$ 2,99; repasse retido por 30 dias. Fonte: https://create.roblox.com/docs/en-us/production/monetization
- **Desenvolvedores pagos em 2025**: "mais de US$ 1,5 bilhão via DevEx" (comunicado de abril de 2026). Fonte: https://about.roblox.com/newsroom/2026/04/roblox-fuels-high-fidelity-games-over-18-players-increases-qualifying-devex-rate-42
- **Recompra na plataforma**: o relatório GameAnalytics cita taxa de recompra mensal de 90%, com base no balanço do 2º trimestre de 2025 (citação de terceiro). Fonte: https://www.gameanalytics.com/cn/reports/2025-roblox-report
- **ARPPU mediano por pagante por dia (plataforma, 2025)**: US$ 0,72 (P50); P75 US$ 3,00; P95 US$ 20,65. Fonte: https://www.gameanalytics.com/cn/reports/2025-roblox-report (dados de jan/2023 a jul/2025; relatório atualizado em 24/08/2026)
- **ARPPU por duração média de sessão (mediana, 2025)**: 0–3 min US$ 0,48; 7–12 min US$ 0,77; 19–24 min US$ 1,71; 25+ min US$ 2,12. Fonte: mesmo relatório.
- **Retenção por duração de sessão (mediana, 2025)**: D1 de 4,31% (0–3 min) a 11,46% (19–24 min); D7 de 0,41% a 1,82% (25+ min). Fonte: mesmo relatório.

## Regras e políticas importantes

- **Probabilidades obrigatórias**: se o item aleatório for comprado com Robux, ou com moeda do jogo comprada com Robux, todas as chances reais devem ser mostradas em porcentagem, somando 100%. Se houver arredondamento, avise. Fonte: https://create.roblox.com/docs/en-us/production/monetization/paid-random-items
- **Compra indireta conta**: chaves, tokens de re-roll e tickets pagos com Robux também exigem odds antes de o usuário gastar a moeda. Fonte: mesma página.
- **Odds dinâmicas**: se um item melhora as chances (ex.: poção de sorte), as probabilidades novas precisam ser mostradas enquanto o efeito estiver ativo. Fonte: mesma página.
- **Itens de lista com mesma chance**: pode informar uma vez no início da lista. Fonte: mesma página.
- **Restrição regional e etária**: usar PolicyService:GetPolicyInfoForPlayerAsync(), com os campos ArePaidRandomItemsRestricted e IsPaidItemTradingAllowed. Se o usuário for inelegível, não pode usar geradores pagos; é preciso oferecer alternativa (caminho gratuito, ordem fixa de resultados, venda direta, ocultar o item, bloquear compra). Fonte: mesma página.
- **Recompensas ganhas sem pagamento**: não exigem divulgação de odds (ex.: baú encontrado no jogo). Fonte: mesma página.
- **Menores de idade**: evite textos de urgência como "GET IT NOW"; prefira "View Item". Fonte: https://create.roblox.com/docs/en-us/production/monetization
- **Descontos**: devem ser genuínos. Um item "em promoção" permanente não é desconto real. Fonte: https://create.roblox.com/docs/en-us/production/monetization
- **Anúncios recompensados**: um post do DevForum sobre política de anúncios diz que, até 4 de maio, implementações independentes de rewarded video deveriam migrar para o formato nativo; ano não confirmado. Requisito de idade e número de jogadores não foram confirmados. Página oficial de rewarded ads retornou 404 na leitura. Fonte: https://devforum.roblox.com/t/new-advertising-policies-standards/4527365 (resumo de busca)
- **Plugins/models**: preço mínimo de US$ 4,99 e US$ 2,99. Fonte: https://create.roblox.com/docs/en-us/production/monetization

## O que evitar

- **Pay-to-win**: a orientação de guias é consistente em favor de cosméticos e conveniência. O número de "30% de abandono" citado por um blog não tem fonte primária. Evidência: média (consenso), sem dado mensurado.
- **Premium como paywall**: a Roblox recomenda não tornar Premium obrigatório, não prometer Robux que o criador não controla e não usar o modal Premium como paywall. Fonte: https://create.roblox.com/docs/en-us/production/monetization/premium-payouts
- **Itens aleatórios sem odds**: viola a regra oficial, mesmo em jogo pequeno.
- **Oferta permanente com cara de promoção**: a Roblox exige descontos genuínos.
- **Monetizar antes de reter**: sem retenção, a monetização não tem público. Os dados mostram que D1 e D7 sobem com duração de sessão. Fonte: GameAnalytics (ver acima).
- **Mensagens de urgência para menores**: ver acima.
- **Ética de F2P**: Neely (2021) argumenta contra microtransações que manipulam jogadores; artigo do DiGRA alerta para escassez artificial e probabilidades opacas; Bateman defende que F2P pode ser ético. Fontes: resumos de busca (sem leitura completa).

## Divergências entre fontes

- **Taxa DevEx base**: blogs citam US$ 0,0035 por Robux (taxa antiga). A página oficial diz US$ 0,0038 desde 05/09/2025. Vale a página oficial.
- **Cashout mínimo**: um resumo de busca diz 100.000 Robux; a página oficial diz 30.000 Earned Robux.
- **Data do anúncio de 42%**: um blog diz 30/04; outro, 02/05. A URL do comunicado é de abril de 2026.
- **Limiar de price optimization**: documentação oficial cita cerca de 60.000 transações em 30 dias. Um comentário no DevForum sugere 100.000 (especulação de comunidade).
- **Data de atualização da página de itens aleatórios**: resumo de busca diz agosto de 2026; a página lida só mostra "© 2026", sem data.
- **Total pago a criadores**: fontes dizem mais de US$ 1 bilhão em 2024–2025; US$ 1,5 bilhão em 2025; e mais de US$ 800 milhões em 2025. Os números não são consistentes; use só o comunicado oficial.
- **Recompra**: um post cita "95% dos que compram Robux recompram" (RDC 2018), via blog de desenvolvedor, sem vídeo ou transcrição.
- **Divisão de receita (70%)**: aparece em resumo de busca, não em página lida.

## Fontes lidas (URLs com 1 linha cada)

1. https://create.roblox.com/docs/en-us/production/monetization/paid-random-items — regras de itens aleatórios pagos, odds, PolicyService (lida).
2. https://create.roblox.com/docs/en-us/production/monetization/price-optimization — requisitos, duração, critério de adoção (lida).
3. https://create.roblox.com/docs/en-us/production/monetization/developer-exchange — taxa DevEx padrão, mínimo, data de mudança (lida).
4. https://create.roblox.com/docs/en-us/production/monetization/18-plus-devex-rate — taxa 0,0054 para 18+ nos EUA a partir de 08/06/2026 (lida).
5. https://about.roblox.com/newsroom/2026/04/roblox-fuels-high-fidelity-games-over-18-players-increases-qualifying-devex-rate-42 — anúncio do aumento de 42% (lida).
6. https://create.roblox.com/docs/en-us/production/monetization — tipos de monetização, descontos, menores (lida).
7. https://create.roblox.com/docs/en-us/production/monetization/premium-payouts — descontinuação do Premium Payouts em 24/07/2025 (lida).
8. https://www.gameanalytics.com/cn/reports/2025-roblox-report — ARPPU e retenção por duração de sessão (lida).
9. https://devforum.roblox.com/t/price-optimization-returned-no-results-after-a-long-period-of-time/4025057 — relato de resultado negativo (resumo de busca).
10. https://devforum.roblox.com/t/new-advertising-policies-standards/4527365 — política de rewarded ads (resumo de busca).
11. https://rolearn.dev/guidance/monetization-fundamentals — retenção antes de monetização (resumo de busca; site de terceiros).
12. https://rowatcher.com/news/developer-products-vs-game-passes-you-re-using-both-wrong — proporção passes/produtos (resumo de busca; terceiros).

Não consegui ler: página oficial de rewarded ads (404), comunicado de price optimization no DevForum (vazio), palestras RDC (sem transcrição), e Deconstructor of Fun (sem análise específica encontrada).
