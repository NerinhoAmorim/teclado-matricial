
# Documentação do Projeto: Controle de LEDs e Buzzer com Teclado Matricial 4x4

Descrição do Projeto

Este projeto implementa o controle de LEDs RGB e um buzzer utilizando um teclado matricial 4x4 conectado a um microcontrolador compatível com a Raspberry Pi Pico. Com base na tecla pressionada no teclado, diferentes ações são executadas, como acender LEDs em cores específicas ou ativar o buzzer.

O código utiliza a biblioteca pico/stdlib.h para gerenciamento de GPIOs e temporização e foi projetado para execução em plataformas baseadas no RP2040.

## Funcionalidades

1. Teclado Matricial
Matriz 4x4: O teclado é configurado em uma matriz 4x4, com as linhas configuradas como saídas e as colunas como entradas com resistores de pull-up.

Mapeamento das Teclas: Cada tecla é mapeada para um caractere correspondente, conforme a tabela abaixo:

1 2 3 A

4 4 5 6 B

7 7 8 9 C

	* 0 # D

    Função iniciar_teclado: Inicializa os pinos GPIO para as linhas e colunas.

Função leitura_teclado: Realiza a varredura do teclado e retorna a tecla pressionada.

2. LEDs RGB

São controlados três LEDs nas cores vermelho, verde e azul, conectados aos pinos 13, 11 e 12, respectivamente.

Função set_leds: Controla os LEDs de forma individual, configurando seus estados (ligado/desligado).

3. Buzzer

O buzzer é controlado pelo pino 21.

Função set_buzzer: Liga ou desliga o buzzer conforme a necessidade.

4. Configuração das Ações por Tecla

As seguintes ações são realizadas com base na tecla pressionada:

Tecla A: Acende o LED vermelho e ativa o buzzer.

Tecla B: Acende o LED azul e ativa o buzzer.

Tecla C: Acende o LED verde e ativa o buzzer.

Tecla D: Acende todos os LEDs (vermelho, azul e verde) e ativa o buzzer.

Tecla #: Desliga todos os LEDs e emite um curto som no buzzer.

Outras teclas: Desliga os LEDs e o buzzer.

Arquitetura do Código

Cabeçalhos e Definições:

Inclusão de bibliotecas padrão (pico/stdlib.h e hardware/timer.h).

Definição dos pinos utilizados para LEDs, buzzer, linhas e colunas do teclado.
## Funções

iniciar_teclado: Configura os pinos do teclado.

leitura_teclado: Realiza a varredura do teclado e identifica a tecla pressionada.

set_leds: Controla os estados dos LEDs RGB.

set_buzzer: Controla o estado do buzzer.

Loop Principal:

Varre o teclado continuamente.

Realiza ações baseadas na tecla pressionada.

Diagrama de Conexões

Componente Pino GPIO

LED Vermelho 13

LED Verde 11

LED Azul 12

Buzzer 21

Teclado Linha 1 8

Teclado Linha 2 7

Teclado Linha 3 6

Teclado Linha 4 5

Teclado Coluna 1 4

Teclado Coluna 2 3

Teclado Coluna 3 2

Teclado Coluna 4 1
## Como Exceutar

1. Pré-requisitos
Microcontrolador Raspberry Pi Pico.

Ambiente de desenvolvimento configurado com o SDK do Raspberry Pi Pico.

Um teclado matricial 4x4.

LEDs (vermelho, verde e azul).

Um buzzer.

Fios jumper e uma protoboard.
## Configuração do Ambiente

Configure o SDK do Raspberry Pi Pico no seu sistema (Windows/Linux/Mac).

Compile o código com o CMake:

Crie uma pasta build:

bash

Copiar

Editar

mkdir build

cd build
## Configure o Projeto

bash

Copiar

Editar

cmake ..

Compile:

bash

Copiar

Editar

make

Carregue o arquivo binário gerado no microcontrolador.
## Execução

Conecte o microcontrolador à protoboard e monte o circuito conforme o Diagrama de Conexões.

Alimente o microcontrolador.

Pressione as teclas no teclado para observar os LEDs e o buzzer respondendo às ações.

Observações

O código utiliza sleep_ms para estabilização após a leitura de teclas, evitando múltiplas leituras indesejadas.

Certifique-se de que os resistores pull-up estejam corretamente configurados no teclado.

Possíveis Melhorias

Adicionar suporte a teclas de combinação.

Implementar padrões de som no buzzer para cada tecla.

Expandir para controlar outros dispositivos.
