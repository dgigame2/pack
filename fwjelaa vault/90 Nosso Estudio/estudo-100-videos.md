---
tags: [estudo, videos, retencao, loops, ui, monetizacao, diversao]
data: 2026-11-19
---
# Estudo dos 100 vídeos (resumos)
Fonte: `transcricoes/<tema>/` — **resumos gerados por IA (Gemini/NotebookLM), não transcrições**. Complementa [[estudo-top20]] e [[melhores-tecnicas]].

## Qualidade das fontes (ler antes)
- **Bons:** retenção (quase todos) e loops — trazem exemplos e números.
- **Rasos:** boa parte de UI, monetização (14–20 só têm "visão geral") e diversão (frases genéricas). Valem como pista, não como evidência.
- **Erro de catálogo:** `loops/05 Dear Game Developers…` é sobre *delta time* em código, não sobre loops.
- **Números que contradizem a documentação oficial (não usar sem conferir):**
  - "Jogador altamente engajado = 16+ verificado e seu jogo entre os 3 primeiros do dia" (DevHex) ≠ oficial (compra mínima no Roblox nos últimos 60 dias).
  - "Payout de 5 Robux por pagante que fica 10 min" (Masty) — não confirmado; o oficial hoje é Creator Rewards sem fórmula pública.
  - "D7 é o maior fator de recomendação" (Vuuk) — a doc oficial lista vários sinais sem peso público.

## O que é novo e útil (com fonte e confiança)
**[F] = oficial/RDC · [M] = criador com números · [f] = opinião**

### Retenção e tempo de jogo
- **Tempo de jogo conta por jogador por dia, com teto de 60 min.** Meta: mais jogadores únicos chegando a ~1 h, em dias diferentes. (Masty [M], bate com rasdev)
- **Gradiente de objetivo:** 1º upgrade nos primeiros **5 min**, os seguintes a cada **10–15 min**. Recompensa "só depois de 3 h" faz desistir. (Masty [M]; MoseyTube: entender o loop em 2–5 min, próximo objetivo em +10–15 [M])
- **Parede de progressão no minuto 10** derrubava o D1 de um jogo real (*Raise an Anomaly*); corrigir subiu o D1 para ~16%. (Masty [M] — o resumo está confuso nos números)
- **Motivos de abandono do loop:** ação sem juice; rebirth que só dá multiplicador sem mecânica nova; autoplay sem nada para preencher; atrito pequeno repetido (ex.: falta botão **"Comprar máximo"**). (Masty [M])
- **Curiosidade:** mostrar áreas/itens bloqueados ("desbloqueia no nível 10", silhuetas). (Masty, DevHex, Roblox [F])
- **Servidor vazio mata:** bots de presença ou mecânica social; em jogo por rodadas, dar o que fazer a quem foi eliminado. (Masty [M])
- **Benchmarks de criador (MoseyTube, *Steal a Superstar*) [M]:** tempo médio > 10 min com anúncio e > 20 min vindo da Home; **D1 12–15%, D7 2–3%**. Os **primeiros 7–14 dias** decidem o jogo — ficar ativo corrigindo.
- **Vuuk [M]:** guardar 30–60k Robux (100–200 créditos) para 1–2 semanas de anúncio; CTR > 1,5% é bom, mirar 2–4%.
- **Recompensa diária:** calendário crescente com prêmio grande no **dia 7** (quando a maioria abandona), 14 e 30. (noobmasterandres [f]) ⚠️ A versão que **zera a sequência** é a que estudos chamam de dark pattern — ver [[melhores-tecnicas]].
- **Missões diárias + recompensa por sequência longa** (ex.: Sol's RNG, 14 dias). (dev_fraudkuna [f])
- **Punição vs recompensa com a mesma matemática:** o WoW trocou "perde XP se jogar demais" por "bônus de descanso" e a reação mudou. Moldar regras como bônus, não multa. (GMTK [M])
- **Oficial Roblox [F]:** D1 baixo = onboarding/loop; D7 baixo = progressão; D30 baixo = falta de end-game. Mostrar a progressão longa logo no início (aspiração).
- **Primeiro minuto (Byte Baxter [f]):** jogando em ≤ 10 s; ensinar fazendo, 1 linha por vez; evitar música alta sem controle, tela de carregamento vazia.
- **Bots inflando CCU** (caso MM2): números falsos e servidores sem humanos derrubam retenção real. (Clemond [M])

### Estratégia de mercado
- **"Oceano roxo" (Tizzy [M]):** alta demanda + execução fraca. Procurar temas com público apaixonado mas jogos mal feitos (bombeiros, aeroporto, socorristas). Alternativa ao clone de tendência.
- **Fases de uma tendência:** 1º no mercado → saturação de cópias que morrem. Quem sobrevive muda título, thumbnail e o loop. (Tizzy [M], doc oficial penaliza clones [F])
- **Regra 80/20:** 80% familiar, 20% novo (AlvinBlox [f]) — bate com o "mudar 20%" do Tizzy e o **hook + anchor** do GMTK.
- **Tendência vs evergreen:** jogo de tendência tem teto de ~2 semanas; um evergreen feito em 2 semanas rende ~US$ 7–8k/mês passivo (Alex Builds Games [M]). Considerar evergreen como segunda via.
- **Volume:** jogos em 2–4 semanas; "lance muitos, alguns acertam". (Vuuk [f])

### Loops e economia
- **Loops em camadas:** segundo a segundo (o toque precisa ser gostoso por si só) → minuto a minuto → hora a hora. (Game Design with Michael [f])
- **Loop = escolha de jogar → ação → momento de descanso** (fogueira, fim do dia). (Apox Fox [f])
- **Economia = fontes, inventários, conversores, ralos, trocas.** (GMTK [M])
- **Progressão direta (números) vs independente (ferramentas novas) vs customizável (builds).** Preferir as duas últimas. (Adam Millard [f])
- **Duas fases que se alimentam** (Dave the Diver: mergulho de dia, restaurante à noite) prende no "só mais um dia". (IGN [f])
- **5 gatilhos (SmartyRBX [f]):** progressão, status, FOMO, maestria, comunidade.

### Monetização
- **Consumíveis > game passes** para receita por jogador (passe é compra única). (MoseyTube [M], US$ 43k)
- **Comprar de volta a sequência perdida** converte aversão à perda em receita (MoseyTube [M]) — ⚠️ eticamente delicado com público infantil.
- **Ler o que mais vende e criar a versão maior** (+10 velocidade vendia → lançar +30 e +100 para baleias). (Tizzy [M], 3× receita)
- **Preço casado com os pacotes de Robux** (ex.: pacote de passes de 1.800 = faixa de US$ 20). (BruceDevs [M])
- **RDC 2025 [F]:** 10 jogadores gastando 100 > 1 gastando 1.000 para a saúde do jogo; levar o novo jogador à primeira compra rápido. Preço regional/gerenciado aumenta gasto sem criar produto novo.
- **RDC 2026 [F]:** assinantes Plus jogam 2× mais e gastam até 7×; **71% do top 100 rodou anúncio patrocinado**; **27% dos jogos com vídeo recompensado tiram > 10% da receita dele**; 87% dos jogadores aprovam vídeo recompensado. Vem aí: lojas personalizadas e teste grátis de game pass.
- **Assinatura barata** (50 Robux/mês) vira piso de receita; muito cara poucos assinam. (Wyrq [f])
- **Starter pack ~49 Robux**; passes com placas físicas perto de onde fazem sentido. (RoBuilder [f])
- **Pay-to-win:** um criador classifica pacote P2W exclusivo como o que mais vende (Alex Builds [f]) — conflita com o consenso de vender conveniência. Para jogo de criança e reputação, eu evitaria.

### UI e diversão (o que se aproveita)
- **Regra de cores 60-30-10**; evitar preto/branco puros; cor forte só para ação/alerta. (Kole Jain [f])
- **UIAspectRatioConstraint + Scale + AnchorPoint** para escalar em todos os aparelhos; `CanvasGroup` para barras de progresso. (vários [f])
- **Figma para desenhar, exportar 4× e montar com ImageLabel.** (vários [f])
- **Hook + anchor** (GMTK): algo inesperado preso a algo familiar. **Juice melhora sempre** (Juice it or lose it). **Pilares de design:** escolher 2–3 tipos de diversão e guiar tudo por eles. (Indie Game Clinic [f])
