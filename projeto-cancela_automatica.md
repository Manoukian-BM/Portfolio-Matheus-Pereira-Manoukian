# Portfolio-Matheus-Pereira-Manoukian

projeto: cancela automatica
data:

1. Tinkercad:

   <img width="880" height="666" alt="image" src="https://github.com/user-attachments/assets/507a673a-6e0b-4c93-b10f-92a0762fc6e7" />

2. Código:
```
#include <Servo.h>

const int ultrassonico = 9;
const int pinoCancela = 11;
const int ledVerde = 12;
const int ledVermelho = 13;

Servo cancela;    
long duracao;     
int distancia;    

void setup() {
  Serial.begin(9600);
  
  // Inicialização do Servo
  cancela.attach(pinoCancela);
  cancela.write(0);
  
  // Configura os pinos dos LEDs como SAÍDA de energia
  pinMode(ledVerde, OUTPUT);
  pinMode(ledVermelho, OUTPUT);
}

void loop() {
  // Configura o pino como SAÍDA para emitir o som
  pinMode(ultrassonico, OUTPUT);
  digitalWrite(ultrassonico, LOW);
  delayMicroseconds(2);
  
  // Envia um pulso curto para acionar o sensor
  digitalWrite(ultrassonico, HIGH);
  delayMicroseconds(5); 
  digitalWrite(ultrassonico, LOW);
  
  // Muda o pino para ENTRADA para "ouvir" o retorno
  pinMode(ultrassonico, INPUT);
  
  // Lê o tempo que o som levou para ir e voltar
  duracao = pulseIn(ultrassonico, HIGH);
  
  // Calcula a distância em centímetros
  distancia = duracao * 0.034 / 2;
  
  // Mostra a distância no Monitor Serial
  Serial.print("Distancia: ");
  Serial.print(distancia);
  Serial.println(" cm");
  
  if (distancia > 0 && distancia < 50) {
    Serial.println("Veiculo detectado! Abrindo cancela...");
    cancela.write(90);
    
    // Sinalização: Verde LIGA, Vermelho DESLIGA
    digitalWrite(ledVerde, HIGH);
    digitalWrite(ledVermelho, LOW);
    
    // Tempo que a cancela fica aberta (3 segundos)
    delay(3000); 
    
  } else {
    // Mantém fechada se não houver carro
    cancela.write(0);
    
    // Sinalização: Verde DESLIGA, Vermelho LIGA
    digitalWrite(ledVerde, LOW);
    digitalWrite(ledVermelho, HIGH);
  }
  
  delay(100);
}
```

3. prática:

   <img width="469" height="402" alt="image" src="https://github.com/user-attachments/assets/4f15e295-0aa9-49f8-98b5-b34ac429feaf" />

   a atividade consistia na simulação de uma cancela que abre ao ver um veículo se aproximar.

4. desafios:

   o uso da nova ferramenta (sensor ultrassônico de distância) foi de certa forma confuso devido ao seu ponto cego e o cálculo de distância

5. aprendizados:

   aprendemos a usar o sensor de distância ultrassônico e desenvolvemos o uso do servo motor
