# Portfolio-Matheus-Pereira-Manoukian

Projeto: semáforo

data: 05/02/2026

1. Tinkercad:

   1.1. elétrica:
   <img width="1317" height="541" alt="Captura de tela 2026-03-26 194252" src="https://github.com/user-attachments/assets/0a1783e3-dd0a-45ac-9be0-5fb832f7bd19" />

   1.2. código:
```
int green_LED = 8;
int yellow_LED = 9;
int red_LED = 10;
int green_LED2 = 5;
int yellow_LED2 = 6;
int red_LED2 = 7;

void setup()	{

  pinMode(green_LED, OUTPUT);  
  pinMode(yellow_LED,OUTPUT);  
  pinMode(red_LED, OUTPUT);  
  pinMode(green_LED2, OUTPUT);  
  pinMode(yellow_LED2,OUTPUT);  
  pinMode(red_LED2, OUTPUT);
  }


void loop()	{
  
  digitalWrite(red_LED, LOW);  
  digitalWrite(yellow_LED, HIGH);  
  digitalWrite(green_LED, LOW);  
  digitalWrite(red_LED2, LOW);  
  digitalWrite(yellow_LED2, HIGH);   
  digitalWrite(green_LED2, LOW);  
  
  delay(2000);  
  
  digitalWrite(yellow_LED, LOW);  
  digitalWrite(red_LED, HIGH);   
  digitalWrite(yellow_LED2, LOW);  
  digitalWrite(green_LED2, HIGH);
    
  delay(2000);  
  
  digitalWrite(green_LED, HIGH);  
  digitalWrite(red_LED, LOW);  
  digitalWrite(green_LED2, LOW);  
  digitalWrite(red_LED2, HIGH);
  
  delay(2000);  
}
```

2. projeto prática:

   <img width="960" height="1280" alt="image" src="https://github.com/user-attachments/assets/af178af7-c50c-4fd6-9bf1-823a980e35ef" />

   O projeto consistia na montagem de um sistema semelhante a um semáforo, que liga as cores verde, amarelo e vermelho, respectivamente, em ordens opostas após determinado tempo

3. Dificuldades:
   Tive certa dificuldade na lógica para sincronizar os LEDs nas cores e ordem certas, que foi facil de resolver graças à minha experiência com lógica de programação.

4. Aprendizados:
   Desenvolvimento do entendimento sobre saídas digitais.






   
