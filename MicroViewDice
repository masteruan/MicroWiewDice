/* * * * * * * * * * * * * *
 * MicroView Dice
 * Giovanni Gentile
 * http://www.projectg.it
 * Connect the Power Supply, and a tilt sensor to A0 input.
 * 
 * * * * * * * * * * * * * */
 
#include <MicroView.h>
const int buttonPin = A0;
boolean buttonState = 0;

void setup()
{
  // initialize the MicroView
  uView.begin();	
  // erase hardware memory inside the OLED controller
  uView.clear(PAGE);
  pinMode(buttonPin, INPUT); // Se aperto parte il dado
  digitalWrite(buttonPin, HIGH);
}

void loop()
{
// randomize roll (1-20), 1 is inclusive and 21 is exclusive
int rolls = random(1, 21);
int buttonState = digitalRead(buttonPin);
delay (200);
    if (buttonState == HIGH) {
      // "roll" the dice, "rolls" times.  
      for(int i = 0; i < rolls; i++)
      {
      //draws a random face on the screen (1-6)
      // 1 is inclusive and 7 is exclusive
      drawFace(random(1, 7)); 
      // wait a quarter of a second before showing the next face
      delay(250); 
      }
    }
  }


// given a number from 1 to 6 it will draw the equivalent face of a dice 
void drawFace(int face)
{
  // clear OLED screen's memory
  uView.clear(PAGE);
  switch (face)
    {
      case 1:   // draw face 1
      uView.rect(8, 0, 48, 48);
      uView.circleFill(32, 24, 4);
      break;
      
      case 2:   // draw face 2
      uView.rect(8, 0, 48, 48);
      uView.circleFill(21, 12, 4);
      uView.circleFill(43, 35, 4);
      break;

      case 3:   // draw face 3
      uView.rect(8, 0, 48, 48);
      uView.circleFill(21, 12, 4);
      uView.circleFill(43, 35, 4);
      uView.circleFill(32, 24, 4);
      break;

      case 4:   // draw face 4
      uView.rect(8, 0, 48, 48);
      uView.circleFill(21, 12, 4);
      uView.circleFill(43, 35, 4);
      uView.circleFill(43, 12, 4);
      uView.circleFill(21, 35, 4);
      break;

      case 5:    // draw face 5
      uView.rect(8, 0, 48, 48);
      uView.circleFill(21, 12, 4);
      uView.circleFill(43, 35, 4);
      uView.circleFill(43, 12, 4);
      uView.circleFill(21, 35, 4);
      uView.circleFill(32, 24, 4);
      break;

      case 6:    // draw face 6
      uView.rect(8, 0, 48, 48);
      uView.circleFill(21, 12, 4);
      uView.circleFill(21, 35, 4);
      uView.circleFill(21, 24, 4);
      uView.circleFill(43, 35, 4);
      uView.circleFill(43, 12, 4);
      uView.circleFill(43, 24, 4);
      break;
      }
    uView.display(); // display the face
  }
