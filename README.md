# Proyecto_Final_Arqui
Proyecto Final Grupo No.6
Marcelo Rodriguez Castañaza 1075321
Pablo Josue Reyes Calderon 1040621
Samer Aranki 1240221

#include <Wire.h>
#include <LiquidCrystal.h>


LiquidCrystal lcd(2, 3, 4, 5, 6, 7);


int sensorHumedad = A0;


int h = 0;

void setup() {
  lcd.begin(16, 2);

  
  pinMode(12, OUTPUT);

   digitalWrite(12, LOW);
}

void loop() {

  int humedad = analogRead(sensorHumedad);

 
  h = map(humedad, 0, 1023, 100, 0);

  if (h <= 80) {

    digitalWrite(12, HIGH);
  } 
 
  else {
    
    digitalWrite(12, LOW);
  }

  
  lcd.setCursor(0, 0);
  lcd.print("Humedad");
  lcd.setCursor(0, 1);
  lcd.print(h);

  
  delay(1000);
}