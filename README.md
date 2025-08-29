# ping_pong_game
The Arduino UNO Ping Pong Game v2.0 simulates a two-player ping pong game on an LCD screen with sound effects and LED feedback.

**INTRODUCTION**

College Name: Government Engineering College Arwal

Project Name: Ping-Pong Game using Arduino Uno

**Component Required**

Component Quantity
Arduino Uno R3        1
NeoPixel              2
Lcd 16*2              1
Pushbutton            5 
1kΩ Resistor          5
220 Ω Resistor        1
Piezo                 1
250 kΩ Potentiometer  1

**PROJECT DESCRIPTION & WORKING**

The Arduino UNO Ping Pong Game v2.0 simulates a two-player ping pong game on an LCD screen with sound effects and LED feedback. Here's a detailed explanation of its working:

1. Setting Up:

• The code starts by including necessary libraries for LCD communication (LiquidCrystal) and NeoPixel LED control (Adafruit_NeoPixel).
• It defines pins connected to various components like push buttons (up/down for each player, start button), piezo buzzer, and NeoPixel LED strips (one for each player).
• During setup, it initializes the LCD screen, displays a title screen, and shows a message asking the player to press the start button.

2. Game Start:

• Once the start button is pressed, the code clears the screen and displays player scores (initially 0).
• It then shows a countdown animation (optional) to build anticipation.


3. Gameplay Loop:

• The main loop (loop()) continuously runs and checks for various conditions.
• It constantly checks if the player paddles are being controlled using the up/down buttons for each player. Separate functions (paddle1Up(), paddle1Down(), paddle2Up(), paddle2Down()) handle these movements within the allowed boundaries on the LCD display.

4. Ball Movement and Collisions:

• The code keeps track of the ball's position (x) on the LCD screen.
• It also maintains a variable (bounce) to indicate the ball's direction (up or down).
• Another variable (direction) stores whether the ball is moving left ('L') or right ('R').


*Ball Movement:*

• Depending on the direction variable, separate functions (ballLeftDown(), ballLeftUp(), ballRightDown(), ballRightUp()) are called to update the ball's position on the LCD display.
• These functions consider bounce direction and adjust the ball's position accordingly. They also handle edge detection (top/bottom of the screen) and update the bounce variable if needed.


*Collision Detection:*

• The code checks if the ball's position (x) coincides with the player paddles' locationon the LCD (paddle1 and paddle2 arrays).
• Separate variables (v1, v2, v3) are used to store the values of the ball and paddlesegments at the collision point.
• If a collision is detected (matching values of v1 and v2 for player 1 or v1 and v3 forplayer 2), the ball's direction changes ('L' to 'R' or vice versa).
• The player who successfully hits the ball receives a point, and a sound effect is playedusing the piezo buzzer (piezoSound() function).

5. Game Over and Restart:

• If the ball goes past a player's paddle (no collision detection), the game ends.
• The code displays a "Game Over" message with the winning player's announcement on the LCD.
• Winner indication is also provided visually using NeoPixel LEDs (one strip lights up green for the winner, red for the loser) along with a sound effect.
• After a short delay, scores are reset to zero, and the game restarts, waiting for the start button to be pressed again.

_**CONNECTIONS**_

**Arduino UNO Connections:**

• Arduino UNO 0 -> NeoPixel LED1 in

• Arduino UNO 1 -> NeoPixel LED2 in

• Arduino UNO 2 -> LCD DB 7

• Arduino UNO 3 -> LCD DB 6

• Arduino UNO 4 -> LCD DB 5

• Arduino UNO 5 -> LCD DB 4

• Arduino UNO 6 -> Paddle1 Up pushbutton terminal 2 and 10KΩ pulldown resistor

• Arduino UNO 7 -> Paddle1 Down pushbutton terminal 2 and 10KΩ pulldown resistor

• Arduino UNO 8 -> Paddle2 Up pushbutton terminal 2 and 10KΩ pulldown resistor

• Arduino UNO 9 -> Paddle2 Down pushbutton terminal 2 and 10KΩ pulldown resistor

• Arduino UNO 10 -> piezoelectric crystal positive.

• Arduino UNO 11 -> LCD Enable

• Arduino UNO 12 -> LCD Register select

• Arduino UNO 13 -> Start pushbutton terminal 2 and 10KΩ pulldown resistor

• Arduino UNO 5v -> LCD VCC, potentiometer terminal 2, NeoPixel LED1 + and NeoPixel LED2 +

• Arduino UNO GND -> LCD GND, potentiometer terminal 1, NeoPixel LED1 G and NeoPixel LED2 G

**LCD connections:**

• Contrast -> potentiometer wiper

• LCD LED Cathode -> 220Ω pullup resistor

• LCD LED Anode -> Arduino UNO GND

**Pushbuttons:**

• Connect all pushbutton's terminal 1 to Arduino UNO 5v.


_**CODE EXPLAINED**_

_setup() Function:_

• Initializes communication with the LCD display and NeoPixel LEDs.

• Sets up input/output pins for push buttons, start button, and piezo buzzer.

• Displays a welcome message and instructions on the LCD screen.

_loop() Function:_

• The main game loop that continuously runs, checking for player interactions and updating the game state.

• Monitors push buttons for paddle movement requests.

• Calls appropriate functions (paddle1Up(), paddle1Down(), paddle2Up(), paddle2Down()) to adjust player paddles on the LCD display based on button presses.

• Manages ball movement logic, including direction ('L' for left, 'R' for right) and bounce state (0 for down, 1 for up).


• Utilizes functions like ballLeftDown(), ballLeftUp(), ballRightDown(), ballRightUp() to update the ball's position and handle edge detection (screen boundaries).

• Implements collision detection between the ball and player paddles, updating scores and playing sound effects using the piezoSound() function.

• Handles game over scenarios and displays the winner on the LCD screen.

• Controls NeoPixel LED colors to visually represent the winner.

• Resets scores and restarts the game after a short delay.

_Environment_

TinkerCAD provides a virtual breadboard environment for simulating the hardware connections. This allows for testing and debugging the code before deployment on the actual Arduino UNO board.

The Arduino IDE is used to write and upload code to the microcontroller.

**Conclusion:**

This project demonstrates the development of a two-player Ping Pong game using Arduino UNO and TinkerCAD. It showcases the integration of various components like LCD display, NeoPixel LEDs, and sound effects to create an interactive and engaging gaming experience.
