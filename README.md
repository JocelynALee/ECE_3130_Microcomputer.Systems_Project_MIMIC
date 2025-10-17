# MIMIC – Memory Game  
**ECE 3130: Microcomputer Systems | Spring 2025**
### Demonstration
Watch a demo of the project here: [MIMIC Memory Game Demonstration](https://youtu.be/KwVrnDVoK-k)

## Overview
**MIMIC** is an interactive memory game programmed in **C** for an **STM32 NUCLEO board**.  
The game challenges players to memorize and repeat LED sequences using push-button inputs.  
It features an LCD display for instructions and scoring, a buzzer for audio feedback, and external LEDs that track the player’s remaining lives.  

## Concept
Players must observe a pattern of blinking LEDs and reproduce the sequence correctly using the corresponding switches.  
Each round adds a new step to the sequence, increasing the difficulty. Players have three attempts before the game ends.  

## Features
- **Randomized LED sequences** that increase in length each round  
- **User input via switches (SW2–SW5)** for pattern replication  
- **LCD display** for menus, countdown, and score updates  
- **Buzzer feedback** for correct/incorrect responses and theme music  
- **Three external LEDs** to represent remaining lives  
- **Replay option** to restart the game after a Game Over  

## Hardware Used
- STM32 NUCLEO-L476RG board  
- Built-in LEDs (LED0–LED3)  
- Three external LEDs (lives indicator)  
- Four push buttons (SW2–SW5, GPIOB pins PB8–PB11)  
- 4×4 Keypad  
- LCD Display (I2C connection)  
- Buzzer (PC9 pin)

## Software Tools
- STM32CubeIDE  
- HAL (Hardware Abstraction Layer) Libraries  
- C Programming Language  

## How It Works
1. Displays a **welcome screen** with theme music.  
2. Prompts player to start using a **keypad button**.  
3. Shows **instructions** and a **countdown** (3-2-1-GO!).  
4. Displays a **random LED sequence** for the player to mimic.  
5. Compares the player’s input to the generated sequence.  
6. If correct → advance to the next round.  
   If incorrect → lose one life (external LED turns off).  
7. Game ends after three failed attempts, displaying **Game Over** and the final score.  
8. Offers the option to replay.  

## Implementation Highlights
- Modular program structure dividing **LCD control**, **buzzer output**, and **game logic**.  
- Random number generation using `srand(HAL_GetTick())` for unique sequences each play.  
- Debounced button inputs and improved user feedback through synchronized LED-button mapping.  
- Structured use of `HAL_Delay()` for timing and display management.  

## Key Learning Outcomes
- Integrating multiple peripherals (LCD, buzzer, keypad, external LEDs) in a single system  
- Debugging timing-sensitive code and hardware communication  
- Using modular functions to manage complex embedded software  
- Applying random number generation and state-based logic in C  

## Acknowledgments
Developed by **Jocelyn Lee, Lauren DeFelice, and Kayla Kohr**  
Under the supervision of **Dr. Tarek  Elfouly**, Tennessee Technological University  
*ECE 3130 – Microcomputer Systems, Spring 2025*
