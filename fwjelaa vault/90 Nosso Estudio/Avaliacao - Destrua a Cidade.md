---
tags: [avaliacao, destrua-a-cidade, decisao]
data: 2026-11-20
fonte: código do repositório (branch carlos) + docs/AUDITORIA.md + [[melhores-tecnicas]]
confianca: análise do código e do plano; o jogo não foi jogado no Studio
---
# Avaliação — Destrua a Cidade (20/11/2026)

## Como está hoje
- **Ideia:** co-op de destruição. Lobby → party → servidor reservado com uma cidade procedural; Fogo, Raio e Vento com 5 níveis que **mudam a mecânica** (bola de fogo → incêndio que se espalha → inferno); partida de 8–10 min que termina e zera; moeda permanente (gemas), nível-base com teto 1,4×, rastros cosméticos, pacotes de gemas.
- **Código:** ~21 mil linhas, cidade montada no cliente pela semente, servidor com autoridade, testes, níveis de qualidade para celular, UI testada em 10 aparelhos. Engenharia de nível profissional.
- **Plano:** 11 etapas; feitas a 1 (fundação), 2 (destruição) e 4 (elementos). Faltam XP/persistência, matchmaking com MemoryStore, tutorial, marcos/economia, progressão permanente, UI, mais 2 cidades e otimização. Nunca foi lançado.

## Pontos fortes
- **Fantasia fortíssima e em uma frase:** "destrua a cidade com fogo, raio e vento". Dá para mostrar na thumbnail e é muito clipável, o que conta como marketing grátis.
- **Demanda comprovada:** física, destruição e ragdoll estão entre os jogos que mais crescem nas paradas (BloxNG Crash Physics em #1, Ragdoll Destruction Playground).
- **Progressão que muda o jogo, não só os números:** é exatamente o que os estudos dizem que retém.
- **Co-op na mesma cidade** entrega o sinal de co-play e momentos sociais.
- **Base técnica pronta para celular**, onde está a maioria dos jogadores.

## Problemas (pela régua dos estudos)
1. **Escopo de projeto grande, não de jogo de tendência.** Foram 11 etapas e várias reescritas (Eat City → desastres → elementos). É o padrão "jogo dos sonhos" que faz jogo nunca sair. Contraria a regra de 1–2 semanas.
2. **Carregamento duplo antes da diversão:** entrar no lobby e depois teleportar para outro servidor. O algoritmo mede o bounce em 0–180 s, e um teleporte nesse intervalo custa caro. Nos jogos que estouram, você já está jogando em segundos.
3. **A partida termina e zera.** O motivo para voltar amanhã (D1, D7, D8–28) depende de uma meta-progressão fraca: gemas, rastros e +40% no máximo. Os sucessos de destruição costumam ser **persistentes**: a cidade regenera e você fica cada vez mais forte e mais rico.
4. **Monetização fraca:** só pacotes de gemas e rastros. Faltam consumíveis ligados ao loop, passes de conveniência e upsell no contexto, que segundo os estudos rendem mais.
5. **Matchmaking próprio (MemoryStore, sessões, reservas)** é caro em tokens e só dá para testar publicado. Com 0 jogadores no começo, matchmaking quase não importa.
6. **Público infantil + trava de 100 jogadores engajados:** vai precisar de orçamento de anúncio, ou de mirar 16+ no começo.
7. **Tendência de física no pico:** o diferencial precisa aparecer na thumbnail (os elementos e a cidade inteira caindo), senão vira mais um.

## Veredito
**A ideia é boa. O plano é errado para o objetivo de vocês.** O jogo está sendo construído como um produto de médio porte (sessões, matchmaking, 3 cidades, 15 níveis de elemento) quando o que dá dinheiro rápido é um **MVP persistente lançado em 1–2 semanas**, medido e iterado.

## O que mudar (recomendação)
**Cortar (por enquanto):** o lugar de lobby, o teleporte, o matchmaking/MemoryStore e a party própria (amigos entram no mesmo servidor pelo botão nativo de seguir amigo); 2 das 3 cidades; o Vento e os níveis 4–5; o pipeline de LOD no Blender; a loja de rastros.

**Manter:** CityGen montada no cliente, CityState/autoridade do servidor, ElementPlan, Feedback, UiLayout/Style, testes, níveis de qualidade.

**Mudar o loop para persistente (estilo simulador de destruição):**
- Um servidor, uma cidade (Garden Village) que **regenera** por bairro quando é destruída. Todo mundo do servidor destrói junto.
- Destruir → dinheiro → **upgrades permanentes** (dano, raio, cooldown) → desbloquear o Raio → bairros/cidades maiores com construções mais fortes → rebirth (multiplicador + algo novo, não só número).
- 1º upgrade em ≤ 5 min, os próximos a cada 10–15; jogando em < 60 s, sem tela de carregamento extra; botão "Comprar máximo".
- Motivo para voltar: progresso salvo, recompensa diária que acumula (sem zerar), evento semanal (ex.: "chuva de meteoros" global).
- Social: leaderboard de destruição, bônus de amigo, os momentos clipáveis.

**Monetização do MVP:** passe 2× dinheiro; passe de auto-lançar (conveniência); consumível "Chuva de Meteoros" ou "Tempestade" por 3 min (contextual, aparece quando o jogador está numa construção forte); starter pack ~49 Robux; preços casados com os pacotes de Robux. Sem pay-to-win pesado (público infantil).

**Lançamento:** vídeo de gameplay na página, 5–10 thumbnails (a cidade explodindo com os 3 elementos), mirar 16+ até ter orçamento para os 100 engajados, update da semana 2 já planejado.

## Próximo passo sugerido
Escrever a lista fechada de "pronto para lançar" do MVP (1–2 semanas) e medir quanto do código atual já cobre cada item.
