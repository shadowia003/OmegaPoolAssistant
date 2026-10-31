# OMEGA Pool Assistant — v0.2 Vision Capture

## Incluído
- Fluxo de consentimento do Android MediaProjection.
- Serviço em primeiro plano para captura contínua.
- ImageReader com aquisição da imagem mais recente.
- Throttling de processamento com meta de 60 amostras por segundo.
- Heurística inicial para localizar uma região semelhante ao feltro verde.
- Overlay neon com estado de captura.
- Base geométrica para tacada reta e reflexão.

## Limitações desta versão
Este código é um protótipo experimental. O reconhecimento de bolas ainda NÃO está implementado de forma confiável: o detector atual não confirma centros/radios e retorna zero bolas confirmadas. A detecção da mesa é uma heurística ampla para feltro verde e pode falhar em outros temas, efeitos, menus ou cores. Caçapas, força específica do jogo e trajetórias reais ainda não são calculadas nem desenhadas. O overlay mostra o estado do detector, não previsões reais.

A captura contínua depende de autorização explícita do usuário em cada sessão, e o Android pode limitar a taxa de quadros. O código solicita a sessão via interface oficial, sem contornar proteções nem injetar código no jogo.

## Compilar
1. Abra a pasta no Android Studio atualizado com Android SDK 36.
2. Aguarde a sincronização Gradle.
3. Instale e abra no dispositivo.
4. Conceda permissão de sobreposição.
5. Toque em "Autorizar captura e iniciar" e aceite a caixa oficial de compartilhamento/captura de tela.
6. O Android exibirá uma notificação persistente enquanto a captura estiver ativa.

## Testes recomendados
- Comece em uma mesa de treino, sem menus sobre a mesa.
- Verifique se a região da mesa aparece delimitada.
- Teste em diferentes temas e brilho.
- Compare o contador de processamento com a taxa real de captura.
- Pare a sessão pelo botão do aplicativo.

## Próximos marcos
- v0.3: segmentação de componentes, detecção circular e classificação de bolas com confiança.
- v0.4: detecção/calibração das seis caçapas e geometria da mesa.
- v0.5: previsão de colisão, rebote e trajetória da branca com parâmetros calibrados.
- v0.6: estimativa de força calibrada empiricamente e interface de calibração.
