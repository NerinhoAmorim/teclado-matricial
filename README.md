# Controle de LEDs e Buzzer com Teclado Matricial 4x4

## 📜 Descrição do Projeto

Este projeto implementa o controle de **LEDs RGB** e um **buzzer**, utilizando um teclado matricial 4x4 conectado a um microcontrolador baseado no **Raspberry Pi Pico**. Dependendo da tecla pressionada no teclado, diferentes ações são executadas, como acender LEDs em cores específicas ou ativar o buzzer.

O código foi desenvolvido em **C** e utiliza a biblioteca `pico/stdlib.h` para gerenciar os GPIOs e temporização, projetado para ser executado em plataformas baseadas no microcontrolador **RP2040**.

---

## ⚙️ Funcionalidades

### 1. **Teclado Matricial**
- **Configuração 4x4**: Linhas configuradas como saídas e colunas como entradas com resistores de pull-up.
- **Mapeamento das Teclas**:
1 2 3 A
4 5 6 B
7 8 9 C

0 # D

- **Funções**:
- `iniciar_teclado`: Configura os GPIOs para as linhas e colunas.
- `leitura_teclado`: Realiza a varredura do teclado e identifica a tecla pressionada.

### 2. **LEDs RGB**
- Controle individual de LEDs (vermelho, verde e azul).
- **Função**:
- `set_leds`: Liga ou desliga LEDs conforme a ação.

### 3. **Buzzer**
- Controlado pelo pino GPIO 21.
- **Função**:
- `set_buzzer`: Ativa ou desativa o buzzer.

### 4. **Configuração de Ações por Tecla**
- **Tecla A**: Acende o LED vermelho e ativa o buzzer.
- **Tecla B**: Acende o LED azul e ativa o buzzer.
- **Tecla C**: Acende o LED verde e ativa o buzzer.
- **Tecla D**: Acende todos os LEDs (vermelho, azul e verde) e ativa o buzzer.
- **Tecla #**: Desliga todos os LEDs e emite um curto som no buzzer.
- **Outras teclas**: Desliga LEDs e o buzzer.

---

## 🏗️ Arquitetura do Código

- **Cabeçalhos e Definições**:
- Inclusão de bibliotecas padrão (`pico/stdlib.h` e `hardware/timer.h`).
- Definição dos pinos GPIO para LEDs, buzzer, linhas e colunas do teclado.

- **Funções**:
- `iniciar_teclado`: Configura os GPIOs do teclado.
- `leitura_teclado`: Lê e retorna a tecla pressionada.
- `set_leds`: Controla os LEDs RGB.
- `set_buzzer`: Controla o buzzer.

- **Loop Principal**:
- Varredura contínua do teclado.
- Execução de ações com base na tecla pressionada.

---

## 🔌 Diagrama de Conexões

| Componente        | Pino GPIO |
|-------------------|-----------|
| LED Vermelho      | 13        |
| LED Verde         | 11        |
| LED Azul          | 12        |
| Buzzer            | 21        |
| Teclado Linha 1   | 8         |
| Teclado Linha 2   | 7         |
| Teclado Linha 3   | 6         |
| Teclado Linha 4   | 5         |
| Teclado Coluna 1  | 4         |
| Teclado Coluna 2  | 3         |
| Teclado Coluna 3  | 2         |
| Teclado Coluna 4  | 1         |

---

## 🚀 Como Executar

### 1. Pré-requisitos
- Microcontrolador **Raspberry Pi Pico**.
- Ambiente de desenvolvimento configurado com o **SDK do Raspberry Pi Pico**.
- Componentes:
- Teclado matricial 4x4.
- LEDs (vermelho, verde e azul).
- Buzzer.
- Fios jumper e uma protoboard.

### 2. Configuração do Ambiente
1. Configure o SDK do Raspberry Pi Pico no seu sistema (Windows/Linux/Mac).
2. Compile o código com o **CMake**:
 - Crie uma pasta `build`:
   ```bash
   mkdir build
   cd build
   ```
 - Configure o projeto:
   ```bash
   cmake ..
   ```
 - Compile:
   ```bash
   make
   ```
3. Carregue o arquivo binário gerado no microcontrolador.

### 3. Execução
1. Conecte o microcontrolador à protoboard e monte o circuito conforme o **Diagrama de Conexões**.
2. Alimente o microcontrolador.
3. Pressione as teclas no teclado para observar os LEDs e o buzzer respondendo às ações.

---

## 📋 Observações
- O código utiliza `sleep_ms` para evitar múltiplas leituras indesejadas de uma tecla.
- Certifique-se de que os resistores pull-up estejam corretamente configurados no teclado.

---

## 🔧 Possíveis Melhorias
- Adicionar suporte a teclas de combinação.
- Implementar padrões de som no buzzer para cada tecla.
- Expandir o projeto para controlar outros dispositivos.

---

**Desenvolvido com foco em eficiência e aprendizado contínuo. Contribuições são sempre bem-vindas!**
