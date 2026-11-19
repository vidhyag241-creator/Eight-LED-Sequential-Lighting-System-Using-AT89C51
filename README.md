# Design-and-Implementation-of-an-Eight-LED-Sequential-Lighting-System-Using-AT89C51-Microcontroller
## Aim
To interface an LED with the AT89C51/8051 microcontroller and blink it continuously using Assembly Language.

## Apparatus Required
AT89C51/8051 Microcontroller, Development Board/Proteus, LED, 330 Ω Resistor, 11.0592 MHz Crystal, Power Supply (5 V), Keil µVision, Proteus.

### Theory
The 8051 microcontroller has four 8-bit I/O ports. An LED connected to Port 2 can be turned ON and OFF by writing logic 0 or logic 1 depending on the connection. A software delay creates the blinking effect.

### Circuit Connections
LED Anode → +5V through 330 Ω resistor, LED Cathode → P2.0 (active LOW) or alternatively P2.0→330 Ω→LED→GND (active HIGH).



### Algorithm
1. Start the program.

2. Configure Port 2 as output.

3. Turn LED ON.

4. Generate delay.

5. Turn LED OFF.

6. Generate delay.

7. Repeat forever.

### 8051 Assembly Program
```
ORG 0000H

START:
   MOV P2,#00H      ; LED ON (active LOW)
   ACALL DELAY
   MOV P2,#0FFH     ; LED OFF
   ACALL DELAY
   SJMP START

DELAY:
   MOV R7,#255
L1: MOV R6,#255
L2: DJNZ R6,L2
   DJNZ R7,L1
   RET

END
```
### Flow of Execution
  Initialize → LED ON → Delay → LED OFF → Delay → Repeat

### Observation
  The LED connected to Port 2 blinks continuously.

## Output 

<img width="941" height="673" alt="Screenshot 2026-10-27 133953" src="https://github.com/user-attachments/assets/4e6a3c6f-fe96-4214-a9d0-ca5106698f90" />

<img width="976" height="613" alt="Screenshot 2026-10-27 133922" src="https://github.com/user-attachments/assets/31ed9c0d-6132-4ec3-9247-424858d13bbd" />

## Result
  The LED blinking program using the 8051 microcontroller was implemented and verified successfully.
