# Prototyping of IOT Workshop 1
# Experiment 1: Performing Logical Operations Using Arduino
## Aim
To perform all logical operations (AND, OR, NOT, XOR, NAND, NOR) using the Arduino controller and verify the outputs in Proteus.

## Components Required
1. Arduino UNO
2. LEDs
3. Resistors
4. Push Buttons / Switches
5. Breadboard
6. Connecting Wires 7.Proteus Software

## Brief Overview of Components
1. Arduino UNO: Microcontroller board used to execute logical operations.
2. LEDs: Used to indicate the output of logical operations.
3. Resistors: Protect LEDs and control current flow.
4. Push Buttons/Switches: Provide input signals for logic operations.
5. Breadboard and Connecting Wires: Used for circuit connections.

## Arduino IDE Program
```
void setup() {
  // put your setup code here, to run once:
  pinMode(2,INPUT);
  pinMode(3,INPUT);
  pinMode(4,OUTPUT);
  pinMode(5,OUTPUT);
  pinMode(9,OUTPUT);
  pinMode(10,OUTPUT);
  pinMode(11,OUTPUT);
  pinMode(12,OUTPUT);
  pinMode(13,OUTPUT);
  
}

void loop() {
  // put your main code here, to run repeatedly:
  int a=digitalRead(2);
  int b=digitalRead(3);
  digitalWrite(4,a&&b);
  digitalWrite(5,a||b);
  digitalWrite(9,!(a&&b));
  digitalWrite(10,!(a||b));
  digitalWrite(11,!a);
  digitalWrite(12,a^b);
  digitalWrite(13,!(a^b));
  
}
```

## Connection Diagram
<img width="1650" height="1275" alt="piot logic_page-0001" src="https://github.com/user-attachments/assets/43f904bc-a3a7-44c1-98e4-3661737a16c4" />

## Proteus Simulation Output
<img width="1279" height="899" alt="Screenshot 2026-05-16 103241" src="https://github.com/user-attachments/assets/bdcb68cf-daaa-4387-b488-b6951685c562" />

# Experiment 2: Displaying Digit “2” on a Seven Segment Display Using Arduino
## Aim
To design an Arduino-based circuit to display the digit “2” on a common cathode seven-segment display and simulate it in Proteus.

## Components Required
1. Arduino UNO
2. LEDs
3. Resistors
4. Push Buttons / Switches
5. Breadboard
6. Connecting Wires
7. 7.Proteus Software

## Brief Overview of Components
1. Arduino UNO: Microcontroller board used to execute logical operations.
2. LEDs: Used to indicate the output of logical operations.
3. Resistors: Protect LEDs and control current flow.
4. Push Buttons/Switches: Provide input signals for logic operations.
5. Breadboard and Connecting Wires: Used for circuit connections.

## Arduino IDE Program
```
void setup() 
{
  // put your setup code here, to run once:
  pinMode(12,OUTPUT);
  pinMode(11,OUTPUT);
  pinMode(10,OUTPUT);
  pinMode(9,OUTPUT);
  pinMode(8,OUTPUT);
  pinMode(7,OUTPUT);
  pinMode(6,OUTPUT);
}
void loop() 
{
  // put your main code here, to run repeatedly:
  digitalWrite(12,HIGH);
  digitalWrite(11,HIGH);
  digitalWrite(10,LOW);
  digitalWrite(9,HIGH);
  digitalWrite(8,HIGH);
  digitalWrite(7,LOW);
  digitalWrite(6,HIGH);
}
```
## Connection Diagram
<img width="1650" height="1275" alt="piot no_page-0001" src="https://github.com/user-attachments/assets/4926c98b-a2c7-4001-a775-8a6099cf4e30" />


## Proteus Simulation and Output
<img width="1282" height="909" alt="Screenshot 2026-05-16 105627" src="https://github.com/user-attachments/assets/31a99ec5-0645-4957-b16f-56d39dd82409" />

# Experiment 3: Interfacing 16×2 LCD with Arduino
## Aim
To interface a 16×2 character LCD with Arduino to display the messages “SEC” and “WELCOME”, and verify the output in Proteus.

## Components Required
1. Arduino UNO
2. LEDs
3. Resistors
4. Push Buttons / Switches
5. Breadboard
6. Connecting Wires 7.Proteus Software

## Brief Overview of Components
1. Arduino UNO: Microcontroller board used to execute logical operations.
2. LEDs: Used to indicate the output of logical operations.
3. Resistors: Protect LEDs and control current flow.
4. Push Buttons/Switches: Provide input signals for logic operations.
5. Breadboard and Connecting Wires: Used for circuit connections.

## Arduino IDE Program
```
#include <LiquidCrystal.h>
LiquidCrystal lcd(2,3,8,9,10,11);
void setup() 
{
  lcd.begin(16,2);
}
void loop() 
{
  lcd.clear();
  lcd.setCursor(5,0);
  lcd.print("SEC");
  lcd.setCursor(0,1);
  lcd.print("WELCOME");
  int i=0;
  for(i;i<15;i++)
  {
    lcd.scrollDisplayRight();
    delay(1000);
  }
}
```

## Connection Diagram
<img width="1650" height="1275" alt="piot 162_page-0001" src="https://github.com/user-attachments/assets/4156d67b-b2eb-49a5-aad3-39a92455a1a1" />

## Proteus Simulation Output
<img width="1284" height="900" alt="Screenshot 2026-05-16 105831" src="https://github.com/user-attachments/assets/ed726ac0-aa08-41bf-9c03-39b5228b08a5" />


# Experiment 4: Controlling the Direction of a DC Motor Using Arduino
## Aim
To control the direction of a DC motor using Arduino and verify clockwise and anticlockwise rotation in Proteus.

## Components Required
1. Arduino UNO
2. DC Motor
3. Motor Driver IC (L293D/L298N)
4. External Power Supply
5. Breadboard
6. Connecting Wires As required
7. Proteus Software

## Brief Overview of Components
1. Arduino UNO: Controls the motor direction.
2 DC Motor: Converts electrical energy into rotational motion.
3. Motor Driver IC: Interfaces the motor with Arduino and controls direction.
4. External Power Supply: Provides sufficient power to the motor.
5. Breadboard and Connecting Wires: Used for circuit assembly.

## Arduino IDE Program
```
const int in1Pin =11;
const int in2Pin =10;
const int swpin =7;
int button_status;

void setup() 
{
  // put your setup code here, to run once:
  pinMode(in1Pin,OUTPUT);
  pinMode(in2Pin,OUTPUT);
  pinMode(swpin,INPUT_PULLUP);
}

void loop() 
{
  // put your main code here, to run repeatedly:
  button_status=digitalRead(swpin);
  if(button_status == 0)
  {
    digitalWrite(in1Pin,LOW);
    analogWrite(in2Pin,100);
    delay(2000);
  }
  else
  {
    analogWrite(in1Pin, 255);
    digitalWrite(in2Pin,LOW);
    delay(2000);

  }
}
```

## Connection Diagram
<img width="1650" height="1275" alt="piot dc_page-0001" src="https://github.com/user-attachments/assets/421dcfcd-590f-43d7-83a6-388c0fb94332" />

## Proteus Simulation Output
<img width="1278" height="903" alt="Screenshot 2026-05-16 105947" src="https://github.com/user-attachments/assets/acb3e93c-c703-4876-8d0d-81b98a14f6eb" />

# Experiment 5: Servo Motor Control Using Arduino
## Aim
To control a servo motor using the Arduino controller and verify its angular movement in Proteus.

## Components Required
1. Arduino UNO
2. Servo Motor
3. Breadboard
4. Connecting Wires
5. Proteus Software

## Brief Overview of Components
1. Arduino UNO: Generates PWM signals to control servo position.
2. Servo Motor: Rotates to specific angular positions.
3. Breadboard and Connecting Wires: Used for hardware setup.

## Arduino IDE Program
```
#include <Servo.h>
Servo myServo;
int servoPin = 10;

void setup() {
  // put your setup code here, to run once:
  myServo.attach(servoPin);
}

void loop() {
  // put your main code here, to run repeatedly:
  myServo.write(0);
  delay(2000);
  myServo.write(90);
  delay(2000);
}

```

## Connection Diagram
<img width="1650" height="1275" alt="piot servo_page-0001" src="https://github.com/user-attachments/assets/5043458a-11c4-442b-9471-9c751f918d5e" />

## Proteus Simulation Output
<img width="1272" height="897" alt="Screenshot 2026-05-16 110035" src="https://github.com/user-attachments/assets/dd249fab-d2e2-4217-8712-8d8032163ee5" />
