# Potenciometro
Biomedica - Lab #4

int led1 = 2, led2 = 5, led3 = 8, led4 = 11, led5 = 13;
int potenciometro = A5;
int dados = 0;

void setup() {
  Serial.begin(9600);
  pinMode(potenciometro, INPUT);
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);  
  pinMode(led3, OUTPUT);
  pinMode(led4, OUTPUT);
  pinMode(led5, OUTPUT);
}

void loop() {
  dados = map(analogRead(potenciometro), 0, 1023, 0, 255);
  Serial.print("Dados: ");
  Serial.println (dados);

  if (dados == 0){
    digitalWrite(led1, LOW);
    digitalWrite(led2, LOW);
    digitalWrite(led3, LOW);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);  }

if (dados > 0 && dados <= 200){
    digitalWrite(led1, HIGH);
    digitalWrite(led2, LOW);
    digitalWrite(led3, LOW);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);  }    

if (dados > 50 && dados <= 400){
    digitalWrite(led1, HIGH);
    digitalWrite(led2, HIGH);
    digitalWrite(led3, LOW);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);  }        

if (dados > 100 && dados <= 600){
    digitalWrite(led1, HIGH);
    digitalWrite(led2, HIGH);
    digitalWrite(led3, HIGH);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);  }}
