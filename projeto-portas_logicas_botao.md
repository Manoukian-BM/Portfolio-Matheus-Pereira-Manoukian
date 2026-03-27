# Portfolio-Matheus-Pereira-Manoukian

projeto: portas lógicas com Push Button (AND, OR, NOT)

data: 26/01/2026

1. Tinkercad:
   <img width="917" height="717" alt="image" src="https://github.com/user-attachments/assets/a2bc9ec9-e362-4023-9483-a982b98db745" />

2. código:
```
// projeto estruturas de repetição
// Autor: Matheus Pereira Manoukian

//definicao de pinos
#define LED 10
#define BUTTON1 8
#define BUTTON2 6
#define BUTTON3 4
#define BUTTONW 2

// estados da FSM
enum Estado { For, While, Do_while, Nenhum };
Estado state = Nenhum; 

void setup() {

//modo dos pinos
  pinMode(LED, OUTPUT);
  pinMode(BUTTON1, INPUT);
  pinMode(BUTTON2, INPUT);
  pinMode(BUTTON3, INPUT);
  pinMode(BUTTONW, INPUT);

//comunicacao serial
  Serial.begin(9600);
  delay(250);
}

void loop() {

//estado for
  if (state == For) {
//monitor serial
       Serial.println("Entrando no FOR");
       for (int i = 0; i < 5; i++) {
//leds durante o for
           digitalWrite(LED, HIGH);
           delay(500);
           digitalWrite(LED, LOW);
           delay(500);
           Serial.print("i: ");
           Serial.println(i);
       }
       state = Nenhum; 

//estado while
  } else if (state == While) {
//monitor serial
       Serial.println("Entrando no WHILE");
       while (digitalRead(BUTTONW) == LOW) {
//leds durante o while
           digitalWrite(LED, HIGH);
           delay(500);
           digitalWrite(LED, LOW);
           delay(500);
       }
       state = Nenhum;


  } else if (state == Do_while) {
       Serial.println("Entrando no DO WHILE");
       do {
         digitalWrite(LED, HIGH);
         delay(500);
         digitalWrite(LED, LOW);
         delay(500);
        } while (digitalRead(BUTTONW) == LOW);
       state = Nenhum;
       
  } else {
       if (digitalRead(BUTTON1) == HIGH) {
         state = For;
       } else if (digitalRead(BUTTON2) == HIGH) {
         state = While;    
       } else if (digitalRead(BUTTON3) == HIGH) {
         state = Do_while;
       }
       if(state != Nenhum) delay(200); 
  }
}
```

3. prática:

   <img width="960" height="1080" alt="image" src="https://github.com/user-attachments/assets/23b6c8f5-f06c-40b6-bfda-3764dd660f0e" />

   projeto consistia no uso de laços de repetição com a condição dp uso de botões.

4. Dificuldades:
  confusão usando função "for" e ao utilizar FSM em cpp

5. Aprendizados:
   Desenvolvimento do entendimento dos laços de repetição e da FSM
   









   
