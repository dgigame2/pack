---
tags: [estudo, videos, disaster-evolution, tornado, analise]
data: 2026-11-20
fonte: 100 resumos em `EstudosYouTube\transcricoes\<tema>\` (IA, não transcrição) + leitura do código do DisasterEvolution
confianca: média (os resumos de UI, monetização 14–20 e diversão são rasos)
---
# Vídeos × Disaster Evolution (tornado)
Releitura dos 100 vídeos **em rodízio** (rodada N = vídeo N de cada tema: retenção → loops → UI → monetização → diversão), agora perguntando só uma coisa: **o que isso muda no jogo do tornado?** Estudo genérico anterior: [[estudo-100-videos]]. Estado do jogo: [[Contexto - Disaster Evolution]].

Legenda: ✅ já temos · ⚠️ risco/falta · 💡 ideia barata · ➖ não serve agora

## Conferido no código (20/11)
- ⚠️ **Nenhum som nem tremida no tornado, no PvP e nas skills.** `client/Feedback.luau` existe (sons, shake, números) mas só a UI antiga chama (moedas, loja). `client/City/*` não tem nenhum Sound/Shake. É o ponto que **mais vídeos repetem** (Masty, dev_fraudkuna, DevHex, Creauctopus, Juice it or lose it, Secrets of Game Feel, Thomas Brush, EDG).
- ⚠️ **Cor por rebirth** (prevista no Design como status) não existe no código.
- ⚠️ **Sem placar** (leaderstats/leaderboard): nada mostra quem é o maior do servidor.
- Curva de XP: até o nv 4 (1º Q) ≈ **34 XP**; até o 8 ≈ **180 XP**; até o 15 ≈ **1.900 XP**. Falta medir **em minutos** jogando.
- Rebirth: nível máximo 15 + rebirths; a forma nova seguinte (Typhoon, nv 19) só chega no **4º rebirth**.

---

## Rodada 1
- **Ret · dev_fraudkuna (guia de retenção):** juice + diária + missão com sequência. → ⚠️ juice falta (acima). 💡 missões diárias simples ("destrua 200 casas", "mate 1 tornado") são baratas com o que já existe (contagem no servidor). Sequência de 14 dias: só se **não zerar**.
- **Loops · SmartyRBX (5 gatilhos):** progressão, status, FOMO, maestria, comunidade. → ✅ progressão (barra, formas); ⚠️ **status quase zero** (sem cor por rebirth, sem placar); maestria = skills Q + mira; comunidade fraca. FOMO: deixar para depois.
- **UI · 10 Cool UI/UX (menus contextuais):** UI aparece só quando precisa. → ✅ botão EVOLVE/REBIRTH já é contextual. ⚠️ a UI antiga (dinheiro, gemas, UPGRADES, LOBBY) é o contrário disso.
- **Mon · Wyrq (todas as estratégias):** assinatura barata vira piso; anúncio imersivo em outdoor. → 💡 a cidade tem prédios: **outdoor de anúncio imersivo** cabe naturalmente (renda sem pedir nada ao jogador). Assinatura: depois.
- **Div · GMTK 10 lições:** "pergunte como as mecânicas criam a sensação". → A sensação alvo é **poder de destruição crescente**. Tudo que não reforça isso (moedas, loja de rastros) sai.

## Rodada 2
- **Ret · Masty (minuto 10):** ⚠️ **"rebirth que só dá multiplicador, sem mecânica nova, mata o jogo"** — é exatamente nosso rebirth 1, 2 e 3 (só +50% XP, +10% dano e +1 nível). 💡 dar algo **novo e visível** em cada rebirth: cor/rastro novo do tornado (status, barato) e/ou um passivo pequeno. Também: 1º upgrade em ≤ 5 min, próximos a cada 10–15 min → medir tempo até nv 4 e nv 8. Servidor vazio mata → ver rodada 16.
- **Loops · Game Design Library (economia):** "Dice a Million": o que sobra vira vantagem na rodada seguinte. → ✅ já fazemos parecido (XP além da barra fica guardado até apertar EVOLVE).
- **UI · 7 erros de iniciante:** fluxo, respiro, ícones consistentes. → ➖ vale na limpeza da UI (fase 5).
- **Mon · Jak (monetizar direito):** nada de passe na tela; placas no mapa; benefício para Premium. → 💡 **bônus Premium** (ex.: +10% XP) é 1 linha e gera Premium Payout.
- **Div · Design Diary (game feel):** ajustar resposta sem mudar a mecânica. → ⚠️ mesmo ponto do som/shake.

## Rodada 3
- **Ret · Stash (D1 a D180):** D1 = onboarding, D30+ = conteúdo/LiveOps; web shop. → ➖ web shop não existe no Roblox. Confirma: planejar a **atualização da semana 2** antes de lançar.
- **Loops · Tim Cain (core loop):** o protótipo tem que mostrar o loop na hora. → ✅ o jogador já nasce tornado destruindo. Bom para o **vídeo da página**: 15 s de destruição crescendo.
- **UI · UX × Game Design:** reduzir carga cognitiva. → ⚠️ HUD hoje: XP, vida, botão Q, BLAST, EVOLVE, LV dos outros + UI velha. Tirar a velha antes de qualquer teste com estranhos.
- **Mon · RDC 2026:** Plus 2× tempo, 7× gasto; 71% do top 100 roda anúncio; vídeo recompensado bem aceito. → 💡 **vídeo recompensado na morte: "assista e mantenha sua barra de XP"**. Transforma a nossa punição em oferta opcional e não cobra Robux de criança. ⚠️ conferir elegibilidade de rewarded video (idade/região) antes.
- **Div · Raph Koster:** diversão = aprender padrões; flow. → O padrão a aprender é **quem eu posso engolir / de quem fujo** (cores verde/vermelho ✅) e quando usar o Q.

## Rodada 4
- **Ret · noobmasterandres (diárias):** calendário crescente, prêmio grande no dia 7. → 💡 sim, mas **sem zerar** a sequência (ver [[melhores-tecnicas]]). Prêmio = XP boost de 15 min (não tem moeda no jogo, então o prêmio tem que ser XP ou cosmético).
- **Loops · Roblox (core loop essentials):** "se o loop não for divertido sozinho, nada salva". → O teste é: **5 min de Breeze destruindo com som e tremida é gostoso?** Fazer esse teste antes de mexer em mais sistema.
- **UI · Dicas Studio:** `CanvasGroup` em barra de progresso. → 💡 barra de XP/vida: conferir se corta certo nos cantos arredondados.
- **Mon · RDC 2025:** 10 pagando 100 > 1 pagando 1.000; levar à 1ª compra rápido. → 💡 produto barato logo cedo: **XP boost 2× de 15 min por ~25–49 Robux** (consumível).
- **Div · Brackeys:** jogador é o motor; comunicação clara; apelo. → ✅ jogador é literalmente o desastre. Comunicação: precisa de **indicação do que dá mais XP** (prédio grande brilha? número de XP saindo?).

## Rodada 5
- **Ret · GMTK (proteger o jogador dele mesmo):** jogadores otimizam a diversão para fora; recompensa > punição (WoW: bônus de descanso). → ⚠️ dois comportamentos previsíveis no nosso jogo: (1) pequenos fogem e só farmam; (2) **grandes acampam o spawn** matando pequenos (sem área segura, só 5 s de escudo). O (2) é um momento de desistência clássico. 💡 respostas baratas: spawn em ponto aleatório longe do maior tornado; **recompensa** por caçar alguém do seu tamanho (bounty no maior do servidor) em vez de punir quem caça pequeno. 💡 "morrer zera a barra" é punição — o vídeo recompensado da rodada 3 e um **bônus de descanso** (voltou depois de 8 h → XP ×2 por 10 min) são a versão recompensa.
- **Loops · Freya (delta time):** fora do tema, mas útil: suavização com lerp precisa de decaimento exponencial. → ⚠️ conferir o movimento do visual/câmera do tornado em FPS baixo (celular).
- **UI · Truques Studio:** AspectRatio, UIPageLayout. → ➖ técnico, usar quando refizer a UI.
- **Mon · Donation board:** ➖ não combina com o jogo.
- **Div · GMTK pensar como designer:** desconstruir. → ➖ genérico.

## Rodada 6
- **Ret · DevHex (250 engajados):** anúncio para **comprar dados**, não sucesso; A/B de thumbnail. → ✅ bate com o plano (fase 0 grátis → teste US$ 30–50). ⚠️ a definição de "engajado" dele está errada (ver [[Trava de idade - 100 jogadores engajados]]).
- **Loops · Roblox (progressão):** metas curta/média/longa integradas ao loop. → ✅ curta = barra; média = forma nova/Q; longa = rebirth/30. ⚠️ falta meta **média entre o nv 8 e o 12** se o ritmo ficar lento — medir.
- **UI · Good/Bad graphic design:** UI diegética. → 💡 o próprio tornado já é a UI de nível (tamanho/cor). Dá para mostrar a vida **no tornado** (cor ficando vermelha) e tirar barra.
- **Mon · MoseyTube $43k:** consumíveis > passes. → 💡 consumíveis que fazem sentido: XP boost, **"guardar barra na morte" (1 uso)**, recarga instantânea do Q. ⚠️ "comprar de volta" com criança: preferir a versão vídeo recompensado.
- **Div · GMTK ideias (hook + anchor):** → anchor = simulador de crescer/rebirth (familiar); hook = **você é o tornado e engole outros tornados**. A thumbnail tem que vender o hook.

## Rodada 7
- **Ret · Vuuk:** guardar 30–60 k Robux de anúncio; CTR > 1,5%; tempo > 10–15 min. → ⚠️ nosso orçamento (R$ 200–1000) é bem menor que isso; usar o anúncio só como teste de dados, como já decidido.
- **Loops · Chains:** ações encadeadas criam tensão. → 💡 **combo de destruição**: destruir vários seguidos em poucos segundos sobe um multiplicador de XP visível ("x5 COMBO"). Barato, puro juice + maestria. ✅ o `Feedback` antigo já tem um tipo "Combo"/"ZoneClear" para reaproveitar.
- **UI · React Luau:** ➖ não mudar a arquitetura de UI agora.
- **Mon · MoseyTube $12k (Guess the Job):** passes 2× + VIP; pagar para recuperar sequência. → 💡 **passe 2× XP** (já previsto) + **VIP** (cor exclusiva + 1,5× XP).
- **Div · BiteMe (aumentar diversão):** feedback em toda ação, tirar tempo morto. → ⚠️ tempo morto nosso: **renascer no spawn e andar até achar cidade** e esperar a cidade voltar (60 s) se o servidor limpou tudo.

## Rodada 8
- **Ret · rasdev:** prender em 30 s, MVP rápido. → ✅.
- **Loops · Michael (3 camadas):** segundo a segundo precisa ser gostoso sozinho. → segundo = andar + prédio caindo (⚠️ sem som); minuto = EVOLVE/Q novo; hora = rebirth/forma nova.
- **UI · How To Fail At UI:** não deixar a UI para o fim. → ⚠️ estamos deixando (a UI velha ainda está lá).
- **Mon · Tizzy (ELI5):** ver o que mais vende e criar a versão maior. → 💡 depois do lançamento: se 2× vender, lançar 3×/5×. Só com dado.
- **Div · Juice it or lose it:** juice melhora 100% das vezes. → ⚠️ mesmo ponto (som, shake, hitstop no prédio caindo, partícula de detrito).

## Rodada 9
- **Ret · AlvinBlox (10 pilares):** jogar o próprio jogo por horas; social; 80/20. → 💡 vocês dois jogarem 30 min juntos é o teste mais barato que existe.
- **Loops · Repetição com variedade:** ⚠️ a cidade se regenera **igual** → 30 s parecidos o tempo todo. 💡 o plano de **regiões** (pequenos x grandes) também resolve variedade: região de casas, de prédios, de fábricas, cada uma com XP diferente.
- **UI · Melhorar UI Studio:** ➖ estético.
- **Mon · Cumin (ética):** → público é criança: evitar P2W pesado e "pague para não perder".
- **Div · Hitstop/som em camadas:** → 💡 prédio grande caindo = som grave + pequena pausa de câmera; casa pequena = pop. O `FeedbackConfig` já tem POP/TIER_UP.

## Rodada 10
- **Ret · App Masters:** deixar o controle mais rápido subiu muito a retenção de um jogo. → ⚠️ WalkSpeed base 16 (igual a um boneco normal) com tornado pequeno pode parecer lento. 💡 testar base 20–22.
- **Loops · Dave the Diver (duas fases):** ➖ fora do MVP.
- **UI · UI como top games (Figma):** ➖ depois.
- **Mon · BruceDevs (25 M Robux):** preço casado com pacotes de Robux. → 💡 ao precificar, olhar os pacotes (ex.: 400/800/1.700).
- **Div · NOBL (10 princípios):** risco e recompensa. → ✅ já temos: XP guardado sem evoluir pode ser perdido na morte (risco) — **deixar isso claro na UI** ("você vai perder X XP").

## Rodada 11
- **Ret · GMTK (sem ser maligno):** mostrar o que vem depois (porta trancada, Metroidvania). → 💡 **faixa de formas** com silhuetas: Breeze ✓ · Dust Devil (LV4) · … · Void Storm (?). Barato e dá a meta longa no 1º minuto.
- **Loops · Apox Fox (momento de descanso):** → ✅ o EVOLVE manual e a janela de rebirth **são** o momento de descanso. ⚠️ precisam de comemoração forte (som, explosão de luz, o tornado crescendo na hora).
- **UI · Escala:** Scale + AspectRatio + AnchorPoint. → ⚠️ conferir botões Q/BLAST no celular (perto do pulo).
- **Mon · RoBuilder:** starter pack 49 Robux com contador. → 💡 starter: 2× XP 30 min + cor de tornado. ⚠️ contador regressivo falso é dark pattern.
- **Div · 5 níveis de jogos Roblox:** ➖ raso.

## Rodada 12
- **Ret · Creauctopus:** nada de anúncio nos primeiros segundos; explicar em 1 frase. → Frase: **"Seja um tornado. Destrua a cidade. Engula os outros."**
- **Loops · GMTK economia:** fontes/ralos. → ✅ XP não é moeda, não precisa de ralo. Se entrar moeda depois, aí precisa.
- **UI · Inventário (Zelda/Doom):** atalhos rápidos. → ✅ teclas R e Q.
- **Mon · Alex (US$ 8k evergreen):** tendência dura ~2 semanas, evergreen fica. → Tornado/desastre é **evergreen-ish** (tema sempre volta); isso é bom para nós.
- **Div · Elegância:** menos mecânica solta, mais profundidade no centro. → ⚠️ 8 skills Q diferentes é muita coisa nova para MVP; ok porque já está feito, mas **não adicionar mais sistemas** antes de testar.

## Rodada 13
- **Ret · SmartyRBX (Maslow):** status/dominância em jogos competitivos. → 💡 placar "maior tornado do servidor" + coroa em cima de quem é o maior (barato, alvo natural de caça = bounty).
- **Loops · Adam Millard (3 progressões):** direta (números) vs independente (ferramentas novas). → ✅ formas com Q novo são progressão independente. ⚠️ rebirths 1–3 são só direta (ver rodada 2).
- **UI · 10× melhor:** ➖.
- **Mon · Alex (tier list, P2W = S):** → ⚠️ não seguir: PvP + P2W com criança afasta. Vender velocidade de progressão e cosmético.
- **Div · Thomas Brush (tamanho, cor, som, poeira, música):** → ⚠️ som e **música** ausentes. 💡 música de fundo que intensifica quando há tornado grande perto.

## Rodada 14
- **Ret · Tizzy (oceano roxo):** cópias morrem; sobrevive quem muda título, thumb e loop. → ✅ nosso diferencial é PvP de tornados + skills; ⚠️ checar [[Disaster Evolution - concorrencia]] para não parecer cópia na thumb.
- **Loops · Extra Credits (Skinner box):** progressão com profundidade, não manipulação. → ✅.
- **UI · Ranking de UIs:** ➖.
- **Mon · 4 formas de renda:** Premium Payouts, produtos, anúncios imersivos. → ✅ cobertos acima.
- **Div · WIRED (fricção):** desafio na medida. → O desafio é o PvP; sem ele o jogo é só um clicker andante.

## Rodada 15
- **Ret · Josh Strife (quit moment):** perda severa de progresso faz desistir; volta depois de meses e se sente perdido. → ✅ nossa morte é branda (nível fica). ⚠️ jogador que volta: mostrar "você é LV 12 · faltam X para o rebirth" ao entrar.
- **Loops · SmartyRBX (ação → recompensa → repetir):** ✅.
- **UI · Básico (UICorner/UIStroke):** ➖.
- **Mon · Slop games:** ➖ raso.
- **Div · waveshine:** loop nos primeiros 30 s + thumbnail. → ✅/fase 5.

## Rodada 16
- **Ret · Clemond (MM2 e bots):** servidor cheio de bots/exploiters destrói retenção. → ⚠️ **o problema inverso é o nosso**: com pouco CCU, o servidor de 6 terá 1–2 pessoas e **o PvP some**. 💡 tornados NPC simples (andam e destroem, dá para engolir) só se o teste mostrar servidor vazio. Não usar para inflar CCU.
- **Loops · Design Doc (level up):** escolher pontos cria build. → ➖ fora do MVP (seria a "árvore" do rebirth).
- **UI · Figma vs Photoshop:** ➖.
- **Mon · Shawnyg (erros):** falta produto barato. → 💡 mesmo que rodada 4.
- **Div · MDA:** estética alvo = **poder + competição**. Decide o que entra.

## Rodada 17
- **Ret · Roblox oficial (D1/D7/D30):** D1 baixo = onboarding; D7 = progressão; D30 = end-game. Mostrar a progressão longa logo no início. → 💡 faixa de formas (rodada 11). End-game = nv 30 + Void Storm; ✅ existe.
- **Loops · Daniel Cook (modelo mental → feedback):** → ⚠️ sem som/número de XP, o jogador não atualiza o modelo "prédio grande = mais XP". 💡 número de XP flutuando quando algo cai.
- **UI · 7 erros de cor (60-30-10):** → aplicar na limpeza.
- **Mon · DOUBLE earnings:** starter pack + passes visíveis no mapa. → 💡 uma placa no spawn.
- **Div · Koster (padrões):** status social = placar.

## Rodada 18
- **Ret · MoseyTube (5 benchmarks):** entender em 2–5 min; tempo > 10 min (anúncio) / > 20 (Home); D1 12–15%, D7 2–3%. → ✅ **usar como meta do teste pago**. "Criar problema e vender solução" ⚠️ cuidado.
- **Loops · automação:** ➖.
- **UI · diegética/espacial:** ✅ "LV n" em cima dos tornados é UI espacial.
- **Mon · Quanto dá para ganhar:** ver [[DevEx - taxa e saque]].
- **Div · Pilares:** escolher 2–3. → **Destruição satisfatória · Crescer · Engolir/fugir.**

## Rodada 19
- **Ret · EDG (4 pilares):** recompensa celebrada, competição, novidade, comunidade. → ⚠️ celebração (som), ⚠️ competição visível (placar). Novidade = formas ✅.
- **Loops · Jailbreak:** ✅ um papel só, mesma progressão.
- **UI · HUDs:** carga cognitiva. → ver rodada 3.
- **Mon · bubDEV slop:** ➖.
- **Div · Vício (Skinner):** → não temos loot aleatório ✅ (e evita a regra de odds, ver [[Itens aleatorios pagos - odds obrigatorias]]).

## Rodada 20
- **Ret · Byte Baxter (60 s):** jogar em ≤ 10 s; sem tela de carregamento vazia; música com controle. → ✅ nasce jogando. ⚠️ carregamento da cidade: mostrar algo enquanto monta. ⚠️ se entrar música, botão de mudo.
- **Loops · Michael (ideias → loops):** ✅.
- **UI · curso curto:** ➖.
- **Mon · Vendi meu jogo:** ➖.
- **Div · "Sua ideia é ruim":** valide o loop antes de expandir. → ⚠️ **regra para nós agora: parar de adicionar sistema e testar.**

---

## O que fazer (ordem, pelo custo × quantos vídeos apontam)
1. **Juice no tornado** (8+ vídeos): som ao destruir (pop pequeno / grave grande), tremida leve proporcional ao tamanho, número de XP flutuando, comemoração no EVOLVE/REBIRTH, som no BLAST/Q/morte/kill. Reaproveitar `client/Feedback.luau` + `FeedbackConfig` (já existem). **Custo baixo.**
2. **Limpar a UI antiga** antes de qualquer teste com outras pessoas (5 vídeos de primeiro minuto/HUD). Custo baixo–médio.
3. **Testar no Studio e medir em minutos:** tempo até nv 4 (meta ≤ 5 min) e nv 8 (≤ 15 min). Ajustar `XpBase`/`WalkSpeed`.
4. **Status visível:** cor por rebirth + coroa/placar do maior do servidor. Resolve o "rebirth só multiplicador" (Masty) e o gatilho de status (SmartyRBX, Maslow). Custo baixo.
5. **Faixa de formas com silhuetas** (meta longa no 1º minuto). Custo baixo.
6. **Anti spawn-camp:** nascer longe do maior tornado. Custo baixo.
7. Monetização (fase 5): Premium +10% XP · passe 2× XP · VIP · consumível 2× XP 15 min · **vídeo recompensado "manter a barra"** (conferir elegibilidade) · outdoor de anúncio imersivo. Sem P2W, sem contador falso, sem cobrar para não perder.
8. Só se o teste mostrar: tornados NPC (servidor vazio), combo de destruição, regiões com tipos de construção.

## Rodada profunda (transcrição completa, 1 por tema) — 20/11
O bloqueio do YouTube passou (20/11). Transcrições inteiras salvas em `EstudosYouTube\transcricoes\completas\`.

**Retenção · Masty, minuto 10 (38 min)**
- ⚠️ Ele cita **"+1 Destroy Everything"**: um jogo de destruição que mostra todas as armas na cutscene inicial (laser, canhão orbital, buraco negro) e estraga a curiosidade. É concorrente direto do nosso tema — ver [[Disaster Evolution - concorrencia]]. Lição: **não mostrar o Void Storm/Black Hole no começo**; mostrar silhueta + "LV 27".
- **Uma mecânica nova a cada ~30 min** (não multiplicador). Nosso ritmo: Q novo no 4, 8, 12, 15 e depois só no 4º rebirth → buraco grande depois do 1º rebirth.
- **Servidor vazio**: ele cita um jogo estilo Territory .io que "só é divertido com 50 pessoas" — é o nosso risco (jogo de engolir com 6 por servidor). Correção comum: bots que dão lugar a pessoas.
- 💡 **Evento aleatório com contador na tela** ("próxima tempestade em 10:00") é o que mais segura tempo de jogo (Bubble Gum, Grow a Garden). No tema tornado é natural: **"Frente de tempestade: XP ×2 por 2 min"**, a cada ~10 min, com relógio no HUD. Barato.
- Na hora de sair, **mostrar o quanto já investiu** (nível, rebirths, tempo).
- Loja: não abrir sozinha; no máximo na 3ª tentativa, 3–5 vezes por sessão. Nada de oferta no meio de luta.
- **Método:** gráfico *New user first session retention* (30 s / 1 min / 5 min; bom = 95% / 87% / 65%). Queda no **1º minuto = lag** → testar em celular barato (a cidade é montada no cliente: suspeito nº 1). Teste de cronômetro com conta nova anotando o que libera a cada minuto. 1 hipótese por atualização, olhar 24 h depois.
- ⚠️ Ele diz "5 Robux por pagante que fica 10 min" e "60 min/dia de teto" — o teto ele diz estar na doc; o valor de 5 Robux continua não confirmado.

**Loops · Roblox, Designing Player Progression (37 min)**
- Nível que não dá nada perde força. ✅ cada nível nosso cresce raio/dano (visível). 
- **PvP: separar novatos de avançados** para o novato não ser esmagado — reforça o plano de **regiões por tamanho**.
- **Calcular duração do conteúdo:** XP médio por dia × dias que cada forma deve durar. Fazer isso depois do teste para Typhoon/Firenado/Void Storm.
- **Não trancar a diversão inicial atrás da progressão:** o Breeze já tem Q (Wind Burst) ✅.
- Fim do conteúdo → **placar e PvP** seguram o jogador. Mais um voto pelo placar.

**UI · GMTK, The Power of HUDs**
- **Prévia (preview):** mostrar onde a ação vai acertar antes de apertar. 💡 skills em linha (Dust Dash, Tidal Surge, Inferno Spiral) precisam de uma **linha/seta de mira** no chão enquanto o Q está pronto.
- **Mostrar só quando importa:** vida só no combate (Ghost of Tsushima). 💡 painel de HP aparece quando leva dano ou tem tornado inimigo perto.
- **Tamanho = vida/força** (Mario): ✅ o tamanho do tornado já comunica o nível.
- **Into the Breach:** o que não dá para mostrar com clareza deve ser simplificado. ⚠️ 8 skills diferentes: se o jogador não entende o que o Q dele faz, simplificar.

**Monetização · RDC 2026 (30 min)**
- ✅ **O próprio criador do Ink Game sugere o mesmo:** vídeo recompensado **na morte** para reviver. Confirma a ideia "assista e mantenha a barra".
- Existe (ou sai em out/2026) **plugin do Studio para vídeo recompensado sem código** e **"entrar com recompensa"** na página do jogo (anúncio antes de entrar, sem mudar o jogo). Bom para nós: custo de token quase zero.
- **Ícone de sacola de compras ligado = 6× mais gasto** de Robux (dado do Roblox, opcional nas configurações).
- **Teste grátis de game pass**: +4% de gasto e compradores. Usar no passe 2× XP.
- Item com **nome, descrição e miniatura bons** pode aparecer na Home/busca. Não deixar produto sem imagem.
- Anúncio com objetivo de ganhos: 2 de 3 jogos que reinvestiram até 4% dos ganhos diários tiveram ROAS > 100%. ⚠️ isso é para quem já ganha; não serve para a nossa fase 0.

**Diversão · Juice it or lose it (15 min)**
- **Som é o juice mais barato e mais ignorado** (demonstração: duas bolas que se atravessam parecem bater só por causa do som). Reforça o item 1.
- O que aplicar no tornado: bloco que **cai, gira e é empurrado** para longe (não só some), **tremida de tela** (o mais forte por esforço), confete/partícula no prédio grande, **tween com overshoot** na barra de XP e no tornado crescendo no EVOLVE.
- 💡 "Olhos em tudo" (personalidade com quase zero arte): um **cosmético de tornado com olhos** que olham para o alvo — bom item de loja para criança.

### O que a rodada profunda mudou na lista
- Item 1 (juice) ficou ainda mais forte; incluir **música** e **som de vento** que cresce com o nível.
- Entra **evento "frente de tempestade" com contador** como item 4,5 (barato e o que mais sobe tempo de jogo segundo Masty).
- Entra **mira das skills** (preview) junto com o teste no Studio.
- Na fase 5, primeiro: **vídeo recompensado na morte** (plugin) + sacola de compras ligada + teste grátis do passe.

## Rodadas profundas 2 e 3 (mais 10 transcrições completas) — 20/11

**Rodada 2**
- **Ret · MoseyTube, Why 90% fail (Steal a Superstar):** gastou só **~US$ 148 em anúncio** até a Home pegar (cabe no nosso orçamento). Números do jogo dele: D1 12%, D7 2%. Rebirth dele **libera coisas** (andares, espaços, velocidade), não só multiplicador. O produto **"Nuke All" (mata todo mundo do servidor)** vende por ser caos social. Olhar a aba de aquisição: entradas por amigo e por busca = boca a boca.
  → 💡 para nós: produto de caos **"Terremoto/Mega Tempestade"**: todos os prédios do mapa caem de uma vez e **todo mundo** ganha o XP do que estava perto (alegria geral, não P2W contra os outros).
- **Loops · Indie Game Clinic, Chains:** o que dá sentido a coletar é **para que** a coleta serve; e "corrente secreta": algo que o jogador esbarra várias vezes até entender. → 💡 **segredo no mapa**: destruir um marco específico (estátua, torre de rádio) solta algo raro (cor de tornado secreta). Gera conversa e vídeo de criança. Depois do MVP.
- **UI · gfxcomet, ranking de UIs:** preto puro, padrão forte demais e barra de rolagem gigante = iniciante; degradê + texto que acompanha a cor do cartão = bom. → só referência para a limpeza.
- **Mon · Alex Builds, tier list (transcrição completa):** **Reviver = nível A, quase S** ("máquina de dinheiro", barato, por impulso). **Troll/caos = S** em jogo que se joga com amigos. Pacote de moeda = D. VIP sozinho = fraco. Cosmético só vende para quem já está muito engajado. **Muitos produtos juntos atrapalham os bons.** Boost barato (≤ 60 Robux) em jogo leve; mais caro quando progredir = vencer os outros (nosso caso). P2W = S para ele, mas ele mesmo diz que "pode arruinar o jogo".
  → 💡 **"Manter a barra na morte" barato (~15–25 Robux) + a mesma coisa por vídeo recompensado.** Poucos produtos, bem colocados.
- **Div · Design Diary, 10 jeitos de game feel:** recuo em quem atira; partícula e **luz** no disparo; **pedaços voando do que é atingido** ("faz mais diferença do que parece"); inimigo **pisca branco e é empurrado**; nada some sem efeito; squash e stretch; **dash com partícula parece mais rápido**; tremida com **opção de desligar** (enjoo).
  → 💡 PvP: a rajada **empurra** o tornado atingido e ele **pisca**; Dust Dash com rastro; botão nas configurações para desligar tremida.

**Rodada 3**
- **Ret · Tizzy, oceano roxo (completa):** a doc oficial diz que jogo com título/imagem parecidos com outros **perde recomendação**. Quem sobrevive à saturação muda título, thumbnail e põe um **twist no tema** (não "pesca", e sim "pesca no gelo"). Thumbnail original dele rendeu mais que a "inspirada".
  → Nosso twist: **você é o desastre e engole outros desastres**. Thumbnail tem que ser nossa (nada parecido com Natural Disaster Survival). Conferir nomes parecidos antes de lançar.
- **Loops · GMTK, economias (completa):** custo de nível crescente (Elden Ring) desestimula farmar o fácil ✅ (temos 1,38^L). **Perder o que carrega ao morrer cria tensão** (runas do Elden Ring) ✅ — é o nosso XP guardado sem evoluir. Exploit da Witcher (vacas que voltam) → nossa cidade volta em 60 s: conferir se **ficar parado ao lado de um prédio que regenera** não vira farm AFK.
- **UI · 10 Cool UI/UX (completa):** **Cuphead mostra na morte o quão perto você estava** → 💡 tela de morte: "você estava a 82% do LV 9" + resumo (prédios destruídos, tornados engolidos). **Resumo no fim** ajuda a decidir; texto que aparece por proximidade, sem apertar botão.
- **Mon · Tizzy, ELI5 (completa):** consumível sobe a métrica **"7-day spend days per user"** (dias diferentes com gasto), que aparece nas recomendações da Home. O produto campeão dele **resolveu uma dor que viu jogando** (jogadores AFK sendo roubados → trava de base 24 h). **3 caminhos de compra** (ícone da loja, "+" ao lado da moeda, loja abre sozinha só na 3ª tentativa, até 3–5×/sessão). Produto físico **onde o jogador mais passa**. **Limitado com estoque** ("só 100") vende por status.
  → Dores do nosso jogo que viram produto: crescer devagar (boost XP), **perder a barra** (manter barra), ser caçado logo ao nascer (escudo maior ao nascer?), querer se exibir (cor limitada). ⚠️ "escudo pago" no PvP fica perto de P2W; só depois de ver se a dor existe.
- **Div · GMTK, Secrets of Game Feel (completa):** **pausa de fração de segundo (hitstop) ao matar**; som grave e alto; **tom que sobe em sequência** (moedas do Mario, Peggle) → 💡 perfeito para destruir em sequência; câmera que **enquadra ameaças próximas**; **coisas grandes**; **permanência** (destroços ficam um tempo, mostram o estrago).

## Minha opinião: o que adicionar (para discutir quando o limite resetar)
**Antes de lançar (obrigatório, barato):**
1. **Juice completo no tornado:** som ao destruir (pop pequeno → estrondo grave nos grandes), **tom subindo em sequência**, tremida proporcional ao tamanho (com opção de desligar), número de XP saindo, pedaços voando, hitstop curto ao matar um tornado, comemoração forte no EVOLVE/REBIRTH, som de vento que cresce com o nível. Reaproveita `client/Feedback.luau`.
2. **PvP que se sente:** rajada empurra e faz piscar quem é atingido; Dust Dash com rastro; seta/linha de mira das skills em linha.
3. **Limpar a UI antiga** (dinheiro, gemas, UPGRADES, LOBBY, CREATE PARTY).
4. **Status:** cor do tornado por rebirth + placar/coroa do maior do servidor.
5. **Tela de morte que motiva:** "você estava a X% do próximo nível" + resumo. Nascer longe do maior tornado.
6. **Silhuetas das formas futuras** ("LV 19 ???"), sem mostrar as skills finais.

**Logo depois do lançamento (semana 2, a atualização já planejada):**
7. **Evento "Frente de tempestade"** com contador no HUD (XP ×2 por 2 min a cada ~10 min). Barato e é o que mais segura tempo.
8. **Monetização enxuta (4–5 produtos, não mais):** manter a barra ao morrer (Robux barato **ou** vídeo recompensado), boost 2× XP 15 min (consumível), passe 2× XP com teste grátis, cor limitada, e talvez o produto de caos "Mega Tempestade" que ajuda todo mundo. Ícone de sacola ligado. Placa no spawn.
9. Premium: +10% XP.

**Só se o teste pedir (não fazer antes):**
- Tornados NPC (se servidor vazio), regiões por tamanho (se novatos morrerem demais), segredos no mapa, missões diárias, combo de destruição.

**O que eu NÃO colocaria:** pacote P2W, pacote de moeda (nem temos moeda), contador falso de oferta, loja abrindo sozinha toda hora, sequência diária que zera, VIP só com emblema, mais skills/formas antes de testar as 8 que já existem.

**Risco que nenhum vídeo resolve:** jogo de engolir com servidor de 6 e pouco CCU pode ter servidor com 1–2 pessoas. Medir no teste pago antes de fazer bots.

## Críticas às fontes
- Quase todos os números são de **criadores vendendo curso/canal** (MoseyTube, Tizzy, Alex) — viés de sobrevivente. Usar como meta de teste, não como promessa.
- Os resumos de UI e diversão são genéricos demais para tirar regra; o que sobra deles é "juice" e "pilares", que já batem com o resto.
- Nenhum vídeo fala de **PvP em jogo de crescer** com servidor pequeno — o maior risco nosso (servidor vazio / spawn camp) não tem evidência a favor ou contra; só o teste diz.
