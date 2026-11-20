# Melhores técnicas: retenção, loops, UI, monetização e diversão
Data: 19/11/2026 · Base: `estudo-top20.md` (20 vídeos) + `notas/*.md` (5 pesquisas em texto, ~44 fontes, sobretudo documentação oficial do Roblox, GameAnalytics, Game Developer, NN/g e artigos acadêmicos). Os 100 vídeos de `videos-pendentes.md` ainda não entraram, por causa do bloqueio do YouTube.

**Como ler a força da evidência:** **[F]** = regra ou dado oficial do Roblox, ou estudo com número · **[M]** = recomendação oficial sem dado, ou dado de terceiro com boa amostra · **[f]** = opinião de criador ou blog.

**Limitações:** as notas foram feitas por agentes Haiku. Várias páginas não abriram (PDFs originais de MDA, Theory of Fun e SDT, threads do DevForum, palestras do GDC) e foram substituídas por resumos. Nada aqui prova causalidade. O que temos são regras da plataforma, correlações e experiência de quem deu certo.

> **Atualização 19/11:** os 100 vídeos foram estudados (resumos de IA) em [[estudo-100-videos]]. O que mais muda aqui: 1º upgrade em ≤ 5 min e os próximos a cada 10–15 min; botão "Comprar máximo"; consumíveis rendem mais que passes; preço casado com os pacotes de Robux; benchmarks de criador D1 12–15% / D7 2–3% / tempo > 20 min vindo da Home; "oceano roxo" (tema com demanda e jogos mal feitos) como alternativa ao clone.

---

## 1. O que mudou ou foi confirmado em relação ao primeiro estudo

- ✅ **Janela de 28 dias confirmada** na documentação oficial: sinais medidos em D1, D2–7 e D8–28, como **médias por usuário** (jogo pequeno não é punido pelo volume) [F].
- ✅ **First play bounce** mede saídas em 0–60 s **e** 61–180 s. Os primeiros 3 minutos contam, não só o primeiro [F].
- ⚠️ **Novo, e importante para quem faz clone:** thumbnail padrão deixa o jogo **inelegível** para a Home, e **visual quase idêntico ao de outros jogos reduz a descoberta** [F]. Confirma por fonte oficial o que o Tap dizia sobre os "Throw Food For X".
- ✅ **DevEx:** US$ 0,0038 por Robux ganho desde 05/09/2025, com saque mínimo de 30 mil (= US$ 114) [F]. Existe uma taxa maior, **US$ 0,0054, para gastos de jogadores 18+ verificados nos EUA** em jogos elegíveis (avatar R15), desde 08/06/2026 [F].
- ❓ **"O criador fica com 70% da venda"** não foi confirmado em página oficial. Confiram antes de fazer as contas.
- ✅ **Premium Payouts acabou** (24/07/2025). Agora é **Creator Rewards**, que paga pelo tempo de membros Premium no jogo, sem fórmula pública [F].
- 📉 **Benchmarks reais do Roblox (GameAnalytics, 2025):** o D1 mediano vai de **4,3%** (sessão média de 0–3 min) a **11,5%** (19–24 min), e o D7 vai de 0,4% a 1,8%. O ARPPU mediano por dia vai de US$ 0,48 a US$ 2,12 conforme a duração da sessão [M].
  - *Leitura crítica:* é correlação. Jogos bons têm sessão longa **e** retêm. Mas a direção é clara: **duração de sessão é o termômetro mais confiável que vocês vão ter.**
  - Comparação: no mobile em geral, o D1 mediano fica em ~22% [M]. **Não usem metas de mobile para Roblox.**

---

## 2. As 15 melhores técnicas para um jogo de tendência de 1–2 semanas
Ordenadas por **impacto ÷ custo** para vocês (2 pessoas, tokens limitados).

| # | Técnica | Por que funciona | Evidência | Custo |
|---|---|---|---|---|
| 1 | **Diversão em segundos, ensinando pela ação** (tooltip contextual, nada de tutorial longo) | O bounce de 0–180 s pesa no algoritmo; o jogador decide cedo | [F] regra + [M] recomendação de "≤5 min" | Baixo |
| 2 | **"Momento de alegria" logo no fim do 1º ciclo do loop** (recompensa clara + juice) | Fecha o primeiro ciclo de antecipação → ação → recompensa | [M] oficial | Baixo |
| 3 | **Recursos iniciais** (moeda ou item de começo) para chegar mais cedo ao loop | Encurta o caminho até a parte divertida | [M] oficial | Baixo |
| 4 | **Teste dos 10 minutos sem recompensa**: alguém jogaria 10 min sem XP, loja ou desbloqueio? | Progressão **amplifica** um loop bom; não salva um ruim | [M] oficial + [f] | Zero (é um teste) |
| 5 | **Celular primeiro**: nada nos cantos inferiores (analógico e pulo), alvos de ~1 cm físico, só o vital na tela, ícones em vez de texto | A maioria joga no celular; o público jovem lê pouco | [F] diretrizes oficiais + [M] NN/g | Baixo |
| 6 | **Funcionar com gamepad** (foco direcional, prompts por dispositivo) | Console é ~30% em alguns jogos grandes; sem foco, quem joga no console nem consegue jogar | [F] oficial + [f] Tizzy | Médio-baixo |
| 7 | **Feedback em toda ação** (som + shake; número só quando informa) | Conecta com o feedback imediato do flow | [M] teoria + [f] prática | Baixo |
| 8 | **Thumbnail e ícone próprios e fiéis ao jogo** (nunca o padrão, nunca quase iguais a outro jogo) | Regra de elegibilidade da Home; a primeira impressão tem que bater com o jogo | [F] | Baixo |
| 9 | **Metas curtas + uma meta longa visível** (barra de progresso com números exatos, prévia do próximo desbloqueio) | Curta dá feedback; longa dá direção para o D7 | [M] oficial + [f] top 100 | Baixo |
| 10 | **Economia com ralos que crescem junto** (o custo do próximo upgrade sobe com a produção; rebirth para subir o teto) | Evita inflação e o "acabou o jogo" | [M] Machinations | Baixo (fica na Config) |
| 11 | **Cada sistema novo precisa melhorar uma parte do loop**, senão corta | Atenção é finita; sistemas concorrentes dividem o jogador | [M] Roblox Connect | Zero |
| 12 | **Motivo social**: jogar com amigo dá vantagem, existe troca ou placar | Co-play intencional é sinal oficial (secundário) | [F] sinal / [M] efeito | Médio |
| 13 | **Monetização certa no dia 1**: passe permanente + produto consumível contextual + starter pack barato | Upsell contextual deu +10% de receita por usuário e +18% de conversão sem perder retenção (RDC/Brookhaven) | [M] caso oficial | Médio-baixo |
| 14 | **Item aleatório pago só com odds certas** (em %, somando 100%, inclusive moeda e chave compradas com Robux, odds dinâmicas com poção de sorte, `PolicyService` para regiões restritas) | É regra; sem isso o jogo pode ser punido | [F] | Médio |
| 15 | **Medir a duração de sessão e o funil** (Player Funnel no onboarding) e corrigir onde as pessoas caem | É o termômetro mais confiável que vocês terão | [M] dados GameAnalytics + [F] ferramenta | Baixo |

---

## 3. O que evitar (com o motivo)

- **Tutorial longo ou bloqueante:** é o contrário da recomendação oficial, e o Zyonic perdeu 2 minutos de sessão com um [F/f].
- **Recompensa diária que zera se o jogador faltar:** estudos acadêmicos classificam isso como dark pattern. O efeito na retenção não foi medido, mas o risco de reputação existe. **Prefiram recompensas que acumulam** ou roleta com cooldown, sem punir quem falta [M].
- **Texto de urgência para menores** ("GET IT NOW") e **promoção falsa** (item "em oferta" para sempre): a diretriz oficial pede para evitar os dois [F].
- **Pay-to-win e Premium como paywall:** há consenso de que vender **conveniência e cosmético** funciona melhor. O número exato de abandono que blogs citam não tem fonte [M/f].
- **Monetizar antes de reter:** sem sessão longa não há quem compre. O ARPPU cresce junto com a sessão [M].
- **Grind vazio:** "a mesma coisa, só que mais difícil e com número maior". A progressão tem que mudar algo que o jogador **sente** [f].
- **Jogar com o desempenho:** travar no join vira bounce, e bounce derruba o jogo no algoritmo [F regra / f relato].
- **Price optimization automático do Roblox:** exige ~60 mil transações em 30 dias. **Não é para vocês agora** [F].

---

## 4. Contradições que continuam abertas

| Tema | Lado A | Lado B | Como eu decidiria |
|---|---|---|---|
| Tempo até a diversão | Roblox: "idealmente ≤ 5 min" | Criadores e blogs: 30–90 s | O bounce mede até 3 min, então mirem **< 60 s** e tratem os 5 min como teto |
| Cadência de update | Roblox: pequenas a cada 2–4 semanas | Criadores de sucesso: patch diário + update semanal | Em jogo de tendência, **semanal no primeiro mês** (a janela de 28 dias recompensa isso) |
| Tamanho do botão | Blogs: 44×44 px | NN/g: ~1 cm físico | Testar no celular real; o tamanho físico manda |
| Recompensa diária | Motor de hábito | Dark pattern | Usar sem punição por faltar |
| Teorias de diversão | Koster, MDA, flow e SDT explicam bem | Evidência fraca ou correlacional; nada estudado em Roblox | Usar como **checklist de design**, não como lei |

---

## 5. Checklist do jogo 1 (juntando os dois estudos)

**Antes de programar**
- [ ] Público definido (criança: precisa vencer a trava de 100 jogadores engajados; 16+: não precisa)
- [ ] Loop em uma frase + o bloco que vocês vão mudar (fantasia ou mecânica única, ~20%)
- [ ] O diferencial **aparece na thumbnail** e não fica parecido com os concorrentes
- [ ] Lista fechada de "pronto para lançar" (1–2 semanas de tokens)

**No jogo**
- [ ] Jogando em < 60 s; tutorial por tooltip; "momento de alegria" no fim do 1º ciclo
- [ ] Recursos iniciais; metas curtas + 1 longa visível; custos que sobem na Config
- [ ] 1º upgrade em ≤ 5 min, próximos a cada 10–15 min; nada de parede no minuto 10; botão "Comprar máximo"
- [ ] Som + shake em toda ação; número só quando informa
- [ ] Celular: nada nos cantos inferiores, botões grandes, só o vital, ícones; gamepad funcionando
- [ ] Progresso salvo; motivo para voltar sem punir quem faltou; bônus de amigo
- [ ] Monetização: 1–3 passes (conveniência/cosmético), consumíveis contextuais (rendem mais que passes), starter pack barato (~49 Robux), preços casados com os pacotes de Robux; odds certas se houver sorteio pago

**No lançamento**
- [ ] Vídeo de gameplay na página; 5–10 thumbnails para teste; ícone próprio
- [ ] Player Funnel no onboarding; acompanhar duração de sessão, bounce e D1
- [ ] Atualização da semana 2 já planejada
- [ ] Fases do orçamento: grátis → teste de US$ 30–50 → só escala com métricas boas

---

## Fontes principais
As URLs completas estão nas seções "Fontes lidas" de cada arquivo em `notas/`. As mais importantes:
- create.roblox.com/docs/discovery e /discovery-faq (algoritmo, bounce, thumbnails)
- create.roblox.com/docs/production/analytics/retention e /engagement (FTUE, metas, cadência)
- create.roblox.com/docs/production/game-design/core-loops e /onboarding
- create.roblox.com/docs/production/publishing/adaptive-design, /ui/cross-platform-design (UI e input)
- create.roblox.com/docs/production/monetization/paid-random-items, /developer-exchange, /18-plus-devex-rate, /price-optimization
- gameanalytics.com — 2025 Roblox Report (D1, D7 e ARPPU por duração de sessão)
- nngroup.com/articles/touch-target-size · gamedeveloper.com (core loops; HUD e visão periférica; Theory of Fun 10 anos depois)
- arxiv.org/html/2412.05039v1 (dark patterns em 1.496 jogos mobile)
