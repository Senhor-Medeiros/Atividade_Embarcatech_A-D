# Projeto 8-A: Controle de LEDs RGB e Display OLED com Joystick

**EMBARCATECH - UNIDADE 04**

## Desenvolvedor
Desenvolvido por Eduardo Medeiros Magalhães

## Links:
[Vídeo no YouTube da execução na placa BitDogLab](https://youtu.be/lCyGTs5S6GU)

---

## 📌 Descrição do Projeto
Este projeto implementa o controle de dois LEDs RGB e de um display OLED SSD1306 utilizando um joystick analógico e a comunicação I2C no Raspberry Pi Pico. O objetivo é explorar o uso do conversor analógico-digital (ADC), modulação por largura de pulso (PWM) e interrupções para criar um sistema interativo de resposta visual à movimentação do joystick.

### ✨ Funcionalidades

- **Controle de LEDs RGB**
  - 🔵 O LED Azul varia seu brilho conforme o eixo Y do joystick.
  - 🔴 O LED Vermelho varia seu brilho conforme o eixo X do joystick.
  - 💡 Ambos os LEDs são controlados via PWM para um efeito de transição suave.

- **Controle do Display OLED SSD1306**
  - 📺 Exibição de um quadrado de 8x8 pixels que se move proporcionalmente à posição do joystick.
  - 🔲 Alternância no estilo da borda do display ao pressionar o botão do joystick.

- **Botões e Interações**
  - 🟢 O botão do joystick alterna o estado do LED Verde.
  - 🎛️ O botão A ativa ou desativa os LEDs controlados via PWM.
  - ⚡ Ambos os botões são gerenciados por interrupções e possuem debouncing via software.

---

## 🔧 Hardware Utilizado

- 🖥️ **Raspberry Pi Pico**
- 💡 **LED RGB** (conectado às GPIOs 11, 12 e 13)
- 🎮 **Joystick analógico** (conectado às GPIOs 26 e 27 para leitura analógica)
- 🔘 **Botão do joystick** (conectado à GPIO 22)
- 🔲 **Botão A** (conectado à GPIO 5)
- 🖥️ **Display OLED SSD1306** (comunicação via I2C nas GPIOs 14 e 15)

---

## 🔌 Esquema de Ligações

- **LED RGB**:
  - GPIO 11 → Canal Vermelho
  - GPIO 12 → Canal Verde
  - GPIO 13 → Canal Azul
  - Todos os LEDs possuem resistores apropriados para limitação de corrente.

- **Joystick**:
  - 🎛️ Eixo X → GPIO 26 (ADC)
  - 🎚️ Eixo Y → GPIO 27 (ADC)
  - 🔘 Botão → GPIO 22 (entrada digital com interrupção)

- **Botão A**:
  - 🔲 GPIO 5 (entrada digital com interrupção)

- **Display OLED SSD1306**:
  - 🔗 SDA → GPIO 14
  - 🔗 SCL → GPIO 15

---

## 🚀 Pré-requisitos

### 🛠️ Ferramentas Necessárias:
1. 🏗️ Ambiente de desenvolvimento **VS Code** configurado com o **Pico SDK**.
2. 📦 Biblioteca **ssd1306** para comunicação com o display OLED.
3. 🔌 Ferramentas para monitoramento de saída serial (exemplo: **Putty** ou **VS Code Serial Monitor**).

### 🛠️ Configuração do VS Code:
1. 📌 Certifique-se de que o **Pico SDK** está corretamente configurado.
2. 🔄 O **CMake** e o **compilador ARM GCC** devem estar instalados.

---

## ▶️ Instruções para Compilação e Execução

1. 📥 Clone ou copie este repositório para o seu ambiente de desenvolvimento.
2. 📂 Navegue até a pasta do projeto.
3. ⚙️ Configure o build com o CMake.
4. 🏗️ Compile o programa.
5. 🔄 Carregue o binário gerado no Raspberry Pi Pico.
6. 🖥️ Abra um terminal serial para monitorar as mensagens enviadas pelo programa.

---

## 🎯 Resultados Esperados

1. **Quando o sistema é iniciado**:
   - 📴 Os LEDs RGB estão desligados.
   - 📺 O display OLED exibe um quadrado de 8x8 pixels centralizado.

2. **Durante a execução**:
   - 🎮 Movendo o joystick:
     - 🔴 O LED Vermelho aumenta/diminui de brilho conforme o eixo X.
     - 🔵 O LED Azul aumenta/diminui de brilho conforme o eixo Y.
     - 📺 O quadrado se desloca no display proporcionalmente aos valores do joystick.
   - 🔘 Pressionando o botão do joystick:
     - 🟢 O LED Verde liga/desliga.
     - 🔲 A borda do display altera entre diferentes estilos.
   - 🔲 Pressionando o botão A:
     - 🔄 Liga/desliga os LEDs RGB controlados via PWM.

---

## 🖥️ Simulação no BitDogLab

O projeto pode ser testado no **BitDogLab**, garantindo que:
- 🎮 O joystick controla corretamente os LEDs RGB e o display OLED.
- 🔘 Os botões ativam/desativam funções conforme esperado.
- 📌 O código esteja otimizado para microcontroladores de baixo consumo.

**📌 Observação**: O código segue as boas práticas de organização e está comentado para facilitar a compreensão e futuras modificações.

---

## 🎉 Conclusão

Este projeto permite explorar conceitos fundamentais de **ADC, PWM, comunicação I2C e manipulação de interrupções** no **Raspberry Pi Pico**. O uso de **hardware real** combinado com simulação no **BitDogLab** permite testar a lógica e garantir a correta funcionalidade.


