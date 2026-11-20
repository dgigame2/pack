# UI/UX — notas de pesquisa

Escopo: UI de jogos Roblox, mobile primeiro, para jogos pequenos de tendência (1–2 semanas). Força da evidência: **forte** = diretriz oficial Roblox; **média** = estudo, revisão de pesquisa ou análise com método; **fraca** = blog, opinião ou dado sem fonte.

## Técnicas (técnica — mecanismo — evidência — fonte)

- **Mobile primeiro, depois adaptar a controle e teclado.** Mecanismo: a maioria dos jogadores está no celular; o layout base já deve funcionar com toque e depois ser estendido para gamepad/teclado. Evidência: **forte**. Fonte: https://create.roblox.com/docs/production/game-design/design-for-roblox
- **Todo botão precisa ser acionável por toque, gamepad e teclado.** Mecanismo: o foco direcional (sticks/D-pad) só funciona se os elementos forem focáveis; ações que só existem com mouse ou toque deixam o console de fora. Evidência: **forte**. Fonte: https://create.roblox.com/docs/production/publishing/adaptive-design
- **Prompts de botão mudam com o dispositivo.** Mecanismo: o jogador precisa saber qual botão físico apertar; o texto "Pinch" (toque) e "Press A" (gamepad) é a referência. Usar `InputActionLabel` ou `GetImageForKeyCode()` mantém o ícone sincronizado. Evidência: **forte**. Fonte: https://create.roblox.com/docs/production/publishing/adaptive-design e https://create.roblox.com/docs/en-us/production/publishing/console-guidelines
- **Alvo de toque com tamanho físico mínimo (~1 cm) e espaçamento.** Mecanismo: a lei de Fitts — alvo pequeno e próximo demora mais e gera toques errados em vizinhos. O estudo citado (Parhi et al., 2006, uso com polegar em tela pequena) sustenta o 1 cm. A recomendação é em tamanho físico, não em pixels, porque a densidade de tela varia. Evidência: **média** (análise de NN/g baseada em estudo e testes qualitativos). Fonte: https://www.nngroup.com/articles/touch-target-size/. Obs.: o "44×44 px" aparece em blogs; é convenção, não diretriz Roblox (evidência **fraca**).
- **Alvos maiores para botões primários.** Mecanismo: ação principal, jogador em movimento ou tela com poucos elementos justificam alvo maior. Evidência: **média**. Fonte: https://www.nngroup.com/articles/touch-target-size/
- **Evitar a zona de controles padrão do celular.** Mecanismo: o joystick virtual e o botão de pular ocupam cantos inferiores esquerdo e direito; colocar info ou botões ali causa toques sobrepostos. Evidência: **forte**. Fontes: https://create.roblox.com/docs/ui/cross-platform-design e https://create.roblox.com/docs/production/publishing/adaptive-design
- **Botões frequentes na faixa de alcance do polegar.** Mecanismo: alcance varia com o tamanho do aparelho (um botão a 40% do topo é alcançável no celular, difícil no tablet). Evidência: **forte** para a regra; o exemplo de 40% é do próprio doc. Fonte: https://create.roblox.com/docs/ui/cross-platform-design
- **Posicionar botões customizados em relação ao botão de pular.** Mecanismo: âncora fixa evita que o layout se desfaça em outras telas. Exemplo oficial: `AnchorPoint (1,1)`, 20 px à esquerda do botão de pular, 0,8 do tamanho. Evidência: **forte** (exemplo). Fonte: https://create.roblox.com/docs/ui/cross-platform-design
- **Usar Scale para responsividade e Offset para tamanhos fixos.** Mecanismo: Scale é porcentagem do pai, Offset é pixel; combinar os dois evita textos e botões desproporcionais. Cuidado: 20 vira 20 px, 0,5 vira 50%. Evidência: **forte**. Fonte: https://create.roblox.com/docs/ui/cross-platform-design
- **Respeitar áreas seguras (ScreenInsets).** Mecanismo: o `ScreenGui` pode ficar sob notch ou sob a barra superior do Roblox. O padrão documentado é o modo que mantém os elementos abaixo da barra; o modo `None` ignora os insets de propósito. Evidência: **forte** para a existência do enum; os papéis de cada valor vieram de resumo de busca do próprio doc, não do texto lido. Fonte: https://create.roblox.com/docs/en-us/reference/engine/enums/ScreenInsets
- **Testar em dispositivo real e no emulador.** Mecanismo: a legibilidade e o alcance só se confirmam no tamanho real. Evidência: **forte**. Fontes: https://create.roblox.com/docs/production/publishing/adaptive-design
- **Texto legível, sem fonte fina ou decorativa, com contraste alto.** Mecanismo: texto pequeno e fino perde legibilidade no celular e sob luz variável. Evidência: **forte** (diretriz) e **média** (visão periférica, ver abaixo). Fonte: https://create.roblox.com/docs/production/publishing/adaptive-design
- **Texto com auto-size e quebra de linha; respeitar o tamanho de texto das configurações de acessibilidade.** Evidência: **forte**. Fonte: https://create.roblox.com/docs/production/publishing/adaptive-design
- **Mostrar só o vital durante a partida; mover o resto para menu recolhível.** Mecanismo: tela pequena com muitos botões fica confusa. Evidência: **forte** (diretriz). Fonte: https://create.roblox.com/docs/production/publishing/adaptive-design
- **Poucos passos para ações-chave; progressive disclosure.** Mecanismo: no controle, cada aperto é um passo extra; reduzir passos ajuda em todas as plataformas. Evidência: **forte**. Fonte: https://create.roblox.com/docs/en-us/production/publishing/console-guidelines
- **HUD para visão periférica: grande, contraste alto, pouco texto, movimento para chamar atenção.** Mecanismo: a periferia resolve mal forma, cor e texto; é boa em detectar movimento e flashes; o crowding atrapalha o reconhecimento quando há objetos parecidos perto. Evidência: **média** (revisão de literatura de visão, sem experimento próprio). Fonte: https://gamedeveloper.com/design/perceiving-without-looking-designing-huds-for-peripheral-vision
- **Animação de pulso ou cor para indicar mudança, sem exagerar.** Mecanismo: sinal sutil é perdido, forte demais puxa o olhar do jogo. Evidência: **média** (mesma revisão). Fonte: a mesma acima.
- **Ensinar olhando, depois confiar na periferia.** Mecanismo: iniciantes precisam olhar diretamente para aprender o elemento. Evidência: **média** (mesma revisão). Fonte: a mesma acima.
- **Ícones e UI visual em vez de muito texto.** Mecanismo: público jovem tem dificuldade com interface muito textual; ícones se traduzem melhor entre idiomas. Evidência: **forte** (diretriz, com motivo declarado). Fonte: https://create.roblox.com/docs/production/game-design/design-for-roblox
- **Recompensa visível cedo no onboarding.** Mecanismo: retorno rápido reduz abandono. Evidência: **fraca** (análise de blog sobre top 100; sem dados). Fonte: https://rowatcher.com/news/what-every-top-100-roblox-game-gets-right-a-design-analysis

## Padrões dos jogos Roblox de sucesso

Não há dado público confiável de desempenho de UI por jogo. O que existe é análise qualitativa de blogs e o uso de padrões que o próprio Roblox recomenda.

- **Inventário na parte inferior da tela.** Muitos jogos seguem isso. Mecanismo: jogadores experientes reconhecem o padrão. Evidência: **forte** como diretriz de consistência; **fraca** quanto a sucesso. Fonte: https://create.roblox.com/docs/production/game-design/design-for-roblox
- **Barra persistente de XP ou contador, e prévia de itens bloqueados.** Descritos como comuns entre os top 100 (ex.: Anime Defenders, Blade Ball). Evidência: **fraca** (relato, sem contagem). Fonte: https://rowatcher.com/news/what-every-top-100-roblox-game-gets-right-a-design-analysis
- **Indicador de progresso com valores exatos** (ex.: "6.400 de 10.000 XP", em Type Soul). Evidência: **fraca** (exemplo único). Fonte: a mesma.
- **Monetização cosmética primeiro.** Exemplo citado: skins em Arsenal. Evidência: **fraca** (exemplo). Fonte: a mesma.
- **Divulgação de taxas de drop** após pressão, como o Pet Simulator 99 em 2024. Evidência: **fraca** (exemplo com data, não verificado). Fonte: a mesma.
- **Chat e lista de jogadores são padrão do core UI.** Os jogos não devem colidir com eles; testar a sobreposição ou desativar. Evidência: **forte**. Fonte: https://create.roblox.com/docs/production/game-design/design-for-roblox

## O que evitar

- **Pop-ups e controles cobrindo a tela no celular.** Os cantos inferiores são de controle padrão; o alvo perto demais gera toques errados. Fontes: https://create.roblox.com/docs/ui/cross-platform-design, https://www.nngroup.com/articles/touch-target-size/
- **Botões pequenos ou juntos.** Alvo menor que ~1 cm físico ou muito próximo de outro. Fonte: https://www.nngroup.com/articles/touch-target-size/
- **Layout só com Scale.** Em celular, fica ilegível. Motivo: escala relativa sem piso de tamanho. Evidência: **fraca** (relato do DevForum, leitura só do snippet). Fonte: https://devforum.roblox.com/t/specific-details-about-ui-scaling-best-practices/3888004 (não lida)
- **UI só com mouse.** Ações sem alternativa de toque ou gamepad. Fonte: https://create.roblox.com/docs/production/publishing/adaptive-design
- **Console esquecido.** Sem foco direcional, sem prompts por dispositivo, e chat desativado em console. Fonte: https://create.roblox.com/docs/en-us/production/publishing/console-guidelines
- **Texto demais, fino ou pequeno.** Fontes: adaptive-design e gamedeveloper (texto em periferia não se lê).
- **Clutter no centro da tela.** Muitos elementos juntos e parecidos se confundem. Fonte: https://gamedeveloper.com/design/perceiving-without-looking-designing-huds-for-peripheral-vision
- **Monetização que bloqueia a vida social.** Servidor privado caro afasta grupos de amigos. Fonte: https://create.roblox.com/docs/production/game-design/design-for-roblox

## Divergências entre fontes

- **Tamanho de toque:** Roblox não publica número. NN/g fala em 1 cm físico; blogs usam 44×44 px. Não são equivalentes (um é físico, outro é pixel lógico). Para o projeto, usar tamanho relativo à tela e testar no celular.
- **Quantidade de elementos persistentes:** um blog sugere revisar se houver mais de 5 elementos fixos (fraca). A diretriz oficial só diz "mostrar só o vital" (forte). Sem número oficial.
- **Visibilidade de HUD:** a revisão de periferia defende HUD mínimo; o estudo de feedback em shooter (KTH, 2024, visto só no snippet de busca) não achou efeito significativo de feedback visual vs. áudio. Ou seja, a evidência para "menos HUD" é de teoria da visão, não de experimento de desempenho.
- **Posição de botões de ação:** blogs sugerem canto inferior central (polegar); a diretriz oficial evita os cantos inferiores por causa dos controles padrão. Conciliação: centro-inferior acima da zona de controle, ou perto do botão de pular, testado no aparelho.

## Fontes lidas (URLs com 1 linha cada)

1. https://create.roblox.com/docs/production/publishing/adaptive-design — diretrizes oficiais de design adaptativo (input, layout, texto, legibilidade).
2. https://create.roblox.com/docs/ui/cross-platform-design — posição/tamanho (Scale/Offset), zonas de controle mobile, alcance do polegar.
3. https://create.roblox.com/docs/en-us/production/publishing/console-guidelines — UI para TV/console, foco, prompts, número de passos.
4. https://create.roblox.com/docs/en-us/reference/engine/enums/ScreenInsets — enum de áreas seguras (valores; descrições vieram de resumo de busca).
5. https://create.roblox.com/docs/production/game-design/design-for-roblox — mobile first, inventário, core UI, monetização.
6. https://www.nngroup.com/articles/touch-target-size/ — tamanho de alvo de toque, Fitts, estudo de Parhi et al. (2006).
7. https://gamedeveloper.com/design/perceiving-without-looking-designing-huds-for-peripheral-vision — HUD para visão periférica (revisão de literatura).
8. https://rowatcher.com/news/what-every-top-100-roblox-game-gets-right-a-design-analysis — padrões de onboarding e HUD de top 100 (análise de blog, dados fracos).

Não lidas com sucesso (fetch vazio, usadas só como snippet de busca): DevForum "Designing UI - Tips and Best Practices" (https://devforum.roblox.com/t/3074034), "Developing for Mobile" (https://devforum.roblox.com/t/developing-for-mobile-a-guide-for-beginner-roblox-creators/3785900), "Design mobile first!" (https://devforum.roblox.com/t/design-mobile-first/3029532), "Handheld ready" (https://devforum.roblox.com/t/handheld-ready-optimize-your-creations-for-any-device/3887726). Consequência: o lado DevForum (2024–2026, com likes) não foi verificado nesta pesquisa; vale reabrir essas threads no navegador. Também não foram lidos guias de Celia Hodent nem GDC.
