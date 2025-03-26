# Projeto: Semáforo com Arduino

## Descrição
Este projeto consiste em simular um semáforo de trânsito utilizando a plataforma Arduino. O semáforo é controlado por três LEDs (verde, amarelo e vermelho) e um botão que simula a troca de sinais. A troca de sinais ocorre a partir da interação com o botão, onde o semáforo muda as cores dos LEDs em um ciclo definido: verde → amarelo → vermelho → verde, reiniciando o ciclo.

## Componentes Utilizados:
+ **Arduino Uno**: Microcontrolador utilizado para controlar os LEDs e ler o estado do botão.
+ **3 LEDs (vermelho, amarelo e verde)**: LEDs que representam as luzes do semáforo.
+ **3 resistores de 220Ω**: Usados para limitar a corrente que passa pelos LEDs e evitar que queimem.
+ **1 botão**: Utilizado para simular a troca de sinal do semáforo.
+ **1 resistor de 10kΩ**: Usado no circuito de pull-down para garantir uma leitura estável do estado do botão.
+ **Fios jumper e protoboard**: Para fazer as conexões entre os componentes e o Arduino.

## Funcionamento do Semáforo:
+ **Início:** O LED verde começa aceso, indicando "siga".
+**Mudança de sinal:** Quando o botão é pressionado, ocorre a seguinte sequência:
  1. O LED verde apaga.
  2. O LED amarelo acende por 1 segundo.
  3. O LED amarelo apaga.
  4. O LED vermelho acende por 3 segundos, indicando "pare".
  5. O LED vermelho apaga e o LED verde acende novamente, reiniciando o ciclo.

## Objetivo do Projeto:
O objetivo desse projeto é simular um semáforo de trânsito utilizando o Arduino, ensinando conceitos de controle de LEDs, leitura de entradas digitais e temporização (utilizando a função `delay()`). O projeto também destaca a importância do uso de resistores para proteger os componentes e garantir que a corrente elétrica seja limitada adequadamente.

## Montagem do Circuito:

1. **Conexão dos LEDs:**
   - O **LED verde** é conectado ao pino digital 4 do Arduino.
   - O **LED amarelo** é conectado ao pino digital 3.
   - O **LED vermelho** é conectado ao pino digital 2.
   - Cada LED é conectado em série com um resistor de 220Ω para limitar a corrente.

2. **Conexão do Botão:**
   - Um terminal do botão é conectado ao pino digital 8 do Arduino.
   - O outro terminal é conectado ao **+5V**.
   - Um resistor de 10kΩ é colocado entre o pino digital 8 e o GND para funcionar como resistor de **pull-down**, garantindo que o pino 8 leia o estado do botão corretamente.

## Código Arduino:

int valorBotao;

void setup(){
	pinMode(13,OUTPUT);
  	pinMode(2,INPUT);
  	pinMode(-11,OUTPUT);
  	pinMode(12,OUTPUT);
}
	
void loop(){
  
  
	valorBotao = digitalRead(2);
  if(valorBotao == 1){
    digitalWrite(13, LOW);
  	digitalWrite(12,HIGH);
    delay(1000);
    digitalWrite(12,LOW);
    digitalWrite(11,HIGH);
    delay(3000);
    digitalWrite(11,LOW);
     
    
  } else {
    digitalWrite(13, HIGH);
  }
  	
}