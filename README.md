# Connecting-nodeMcu-with-LCD-screen

![image](https://github.com/dennisngugiwambui/Connecting-nodeMcu-with-LCD-screen/assets/112067611/1efd5e82-050b-4d88-a4ce-ff2996a054d6)

# Connections:

# GND (Ground):

Connect the GND pin of the LCD screen adapter to any GND pin on the NodeMCU.
Connect the GND pin of the LED 1080R7 to the GND pin on the NodeMCU as well.
# VCC (Voltage Supply):

Connect the VCC pin of the LCD screen adapter to a 5V pin on the NodeMCU.
If the NodeMCU doesn't have a 5V pin, you may need an external power supply or a voltage regulator to supply the required voltage for the LCD screen adapter.
# SDA (Serial Data) and SCL (Serial Clock):

These pins are used for I2C communication.
Connect the SDA pin of the LCD screen adapter to the SDA pin (D2) on the NodeMCU.
Connect the SCL pin of the LCD screen adapter to the SCL pin (D1) on the NodeMCU.
LED 1080R7:

# Connect the LED 1080R7 to a 7V power source.
The resistor (R7) should be connected in series with the LED, ensuring the LED receives the correct current.
Connect one end of the LED to the 7V power source.
Connect the other end of the LED to the resistor, then connect the other terminal of the resistor to GND on the NodeMCU.


# code

```
#include <Wire.h> // This library is already built in to the Arduino IDE
#include <LiquidCrystal_I2C.h> //This library you can add via Include Library > Manage Library > 
LiquidCrystal_I2C lcd(0x3F, 16, 2);

void setup()
{
 Wire.begin(D2, D1); //(SDA, SCL) 
 lcd.init();  // initializing the LCD
 lcd.backlight(); // Enable or Turn On the backlight

lcd.setCursor(4, 0); //(Column 5 out of 16 and Row 1 out of 2)
lcd.print("Mindstorm"); // Start Printing
lcd.setCursor(3, 1);//(Column 4 out of 16 and Row 2 out of 2)
lcd.print("Engineering"); // Start Printing
}
void loop()
{
 // No Action!
}

```


![WhatsApp Image 2024-03-14 at 2 47 51 PM (1)](https://github.com/dennisngugiwambui/Connecting-nodeMcu-with-LCD-screen/assets/112067611/393891d2-fe05-41ca-9c5b-3f0bc23d6958)


![Uploading WhatsApp Image 2024-03-14 at 2.47.51 PM.jpeg…]()



