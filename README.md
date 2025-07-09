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

**OUTPUT** : 
