# 4x4-Keypad-Interface-with-LCD-Display-using-Arduino

**NAME**: ADITYA GANGURDE
**DOMAIN**: Embedded Systems
# DESCRIPTION : This project demonstrates how to interface a 4x4 matrix keypad with an LCD (16x2) display using an Arduino board. The system captures key presses from the user via the keypad and displays the corresponding character on the LCD.

When the user presses a key on the keypad, the Arduino reads the input and displays it on the second row of the LCD screen. After a short delay (500 milliseconds), the screen is cleared and prompts the user again with “Enter:” for the next input.

The hardware connections include:
1.A 16x2 LCD connected to digital pins 2 through 7 for data and control signals.
2.A 4x4 matrix keypad connected to digital pins 0, 1, 8, 9 (columns) and 10–13 (rows).
3.The Keypad library is used to simplify reading the matrix keypad, and the LiquidCrystal library controls the LCD.

Applications:
1.Password entry systems
2.Menu selection interfaces
3.DIY calculators or control panels
4.Entry-level learning project for embedded systems and HMI (Human-Machine Interface)

**OUTPUT** : https://drive.google.com/file/d/1X-KHNpIVaW1yCvPOcHiNMHdZVkmjIMng/view?t=5 

**CODE** : 
#include <Keypad.h>
#include <LiquidCrystal.h>

// Initialize the LCD with the numbers of the interface pins
const int rs = 7, en = 6, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

// Define the Keypad layout
const byte ROWS = 4; // Four rows
const byte COLS = 4; // Four columns
char keys[ROWS][COLS] = {
  {'1', '2', '3', 'A'},
  {'4', '5', '6', 'B'},
  {'7', '8', '9', 'C'},
  {'*', '0', '#', 'D'}
};

byte rowPins[ROWS] = {13, 12, 11, 10};    // Connect to the row pins of the keypad
byte colPins[COLS] = {9, 8, 1, 0}; // Connect to the column pins of the keypad

// Create the Keypad object
Keypad keypad = Keypad(makeKeymap(keys), rowPins, colPins, ROWS, COLS);

void setup() {
  // Set up the LCD's number of columns and rows
  lcd.begin(16, 2);
  lcd.print("Enter: ");
}

void loop() {
  char key = keypad.getKey();

  if (key) {
    // Print the key value on the LCD
    lcd.setCursor(0, 1);
    lcd.print(key);
    delay(500); // Delay for readability
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("Enter: ");
  }
}
