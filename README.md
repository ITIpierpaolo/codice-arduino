# codice-arduino
#define GPIO_LED 6
#define GPIO_BUTTON1 8
#define GPIO_BUTTON2 12
int temp = 0;
#define DELAY 200

void setup(){
  pinMode (GPIO_LED, OUTPUT);
  pinMode (GPIO_BUTTON1, INPUT_PULLUP);
  pinMode (GPIO_BUTTON2, INPUT_PULLUP);
  Serial.begin(9600);
}
void loop(){
  int p1 = !digitalRead(GPIO_BUTTON1);
  int p2 = !digitalRead(GPIO_BUTTON2);
  if(p1 == 1 && temp != 255){
  temp++;
  }
  if(p2 == 1 && temp !=0){
    temp--;
  }
  analogWrite (GPIO_LED, temp);
  Serial.println(temp);
  delay(DELAY);  
}
