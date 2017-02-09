//*****ARDUİNO BEY****
//****MUHAMMED ALİ ÖZEN***
#include <LCD5110_Basic.h>

LCD5110 myGLCD(8,9,10,11,12);
extern uint8_t SmallFont[];
extern uint8_t MediumNumbers[];
extern uint8_t BigNumbers[];
int isik = 0;

void setup()
{
  pinMode(A0, INPUT);
  myGLCD.InitLCD();
  myGLCD.setContrast(70);
}

void loop()
{
    myGLCD.clrScr();
    myGLCD.setFont(SmallFont);
    myGLCD.print("ORTAM ISIGI:",5,1);
    
    isik = analogRead(A0);
    isik = map(isik,0,1023,0,100);
   myGLCD.setFont(BigNumbers);
   myGLCD.printNumI (isik,25,20);
  delay(200);
 
}
