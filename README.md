# Projeto de Controle de LED com STM32

![C](https://img.shields.io/badge/language-C-green)
![License](https://img.shields.io/badge/license-MIT-blue)
![Status](https://img.shields.io/badge/status-Development-yellow)

Este projeto foi desenvolvido utilizando a placa STM32, com o objetivo de controlar LEDs e comunicar com o microcontrolador via USART. Ele envolve a interação com um teclado matricial para selecionar ações, e a manipulação de LEDs com base nas entradas recebidas. Além disso, o código também permite a comunicação via USART para responder a comandos externos.

## Funcionalidades

1. **Controle de LEDs**: O projeto controla dois LEDs (azul e verde) conectados à placa STM32. Os LEDs podem ser ativados ou desativados com base nas entradas de um teclado matricial ou comandos via USART.

2. **Interação com Teclado Matricial**: Um teclado matricial foi configurado para que o usuário possa pressionar as teclas que acionam diferentes funções, como alternar os LEDs ou enviar dados via USART.

3. **Comunicação USART**: O microcontrolador está configurado para se comunicar via USART. Dependendo dos comandos recebidos (como 'a', 'v', ou '1'), diferentes ações são realizadas, como a troca de LEDs ou a resposta com o tempo de execução.

4. **Temporizador com Timer 2**: O código utiliza o Timer 2 para gerar interrupções e realizar o controle temporizado. Isso permite, por exemplo, alternar a exibição de mensagens no display LCD ou manipular os LEDs com precisão.

## Descrição do Hardware

- **LEDs**: Dois LEDs (azul e verde) são controlados pelas portas GPIO de um microcontrolador STM32.
- **Teclado Matricial**: Um teclado matricial é utilizado para capturar entradas de usuário e acionar determinadas funções no código.
- **USART**: A comunicação serial é realizada utilizando a interface USART do STM32, permitindo a troca de dados entre o microcontrolador e um dispositivo externo.
- **Temporizador**: O Timer 2 é configurado para gerar interrupções que gerenciam o tempo e permitem a realização de ações periódicas no sistema.

## Como Funciona

1. **Inicialização do Sistema**: O código começa com a configuração dos pinos GPIO e a ativação dos periféricos necessários, como o Timer 2 e o USART.
   
2. **Leitura do Teclado Matricial**: Durante a execução do programa, o teclado matricial é constantemente verificado. Quando uma tecla é pressionada, o código identifica qual tecla foi pressionada e executa a ação associada.

3. **Interrupções USART**: Sempre que o USART recebe um dado, ele aciona uma interrupção que verifica o comando recebido e executa a ação correspondente (como alterar o estado dos LEDs ou enviar dados de tempo).

4. **Controle dos LEDs**: Dependendo das interações do usuário, os LEDs podem ser alternados para exibir diferentes estados, como indicar uma operação em andamento ou uma falha (com base nos comandos recebidos via USART ou teclado).

## Funcionalidades de Comunicação

- **Comando 'a'**: Altera os LEDs para mostrar o LED azul aceso e o verde apagado.
- **Comando 'v'**: Altera os LEDs para mostrar o LED verde aceso e o azul apagado.
- **Comando '1'**: Exibe o tempo de execução no terminal via USART.

## Compilação e Execução

Para compilar o código, utilize um compilador adequado para STM32, como o GCC para ARM:

```bash
make
