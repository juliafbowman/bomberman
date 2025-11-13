# Bomberman Game - Wearables and Nearables Project

A two-player Bomberman-style game developed for the Wearables and Nearables class (Fall 2024) using Processing and Arduino hardware controls.

<img width="795" height="597" alt="Screenshot 2025-11-12 at 11 16 26 PM" src="https://github.com/user-attachments/assets/2b1fbc6e-7d62-40cf-8138-22ffd1c7a05e" />

## Overview

This is a classic bomb-placement battle game where two players compete to eliminate each other using strategically placed bombs. The game features animated characters, collectible power-ups, destructible walls, and sound effects.

## Features

- **Two-Player Gameplay**: Competitive multiplayer with distinct character animations
- **Arduino Integration**: Players controlled via custom Arduino hardware (joystick/buttons)
- **Power-Up System**:
  - **Stars**: Increase bomb explosion range (max 5)
  - **Speed Shoes**: Boost player movement speed
- **Dynamic Map**: Procedurally generated destructible walls
- **Audio System**: Background music, sound effects, and victory themes
- **Animated Sprites**: GIF-based character animations for all movement directions
- **Strategic Gameplay**: Limited bombs (3 per player), timed explosions, and tactical positioning

![output3](https://github.com/user-attachments/assets/c3a6da16-cc7e-4293-a76d-e229b6f818b6)

## Hardware Requirements

- **Arduino board** (connected via serial @ 115200 baud)
- **Joystick/directional buttons** for Player movement (UP, DOWN, LEFT, RIGHT)
- **Bomb button** for Player bomb placement

### Note: 
- This can also be played without the Arduino hardware, using keyboard inputs instead

## Software Requirements

- Processing 3.x or 4.x
- Required Processing Libraries:
  - `processing.serial.*` - Serial communication with Arduino
  - `gifAnimation.*` - GIF animation support
  - `ddf.minim.*` - Audio playback

## Game Assets

The game requires the following assets in the sketch directory:

### Images
- `bg.png` - Background image
- `wall1.png` through `wall5.png` - Destructible wall tiles

### GIF Animations

**Player 1 (Feng):**
- `fengs.gif` (down/idle)
- `fengw.gif` (up)
- `fenga.gif` (left)
- `fengd.gif` (right)

**Player 2 (Pao):**
- `paos.gif` (down)
- `paow.gif` (up)
- `paoa.gif` (left)
- `paod.gif` (right)
- `paotu.gif` (idle)

**Items:**
- `bomb.gif` - Bomb animation
- `star.gif` - Power-up star
- `speed_shoes.gif` - Speed boost item

### Audio Files
- `start.wav` - Startup music
- `bg.wav` - Background loop
- `win.wav` - Victory music
- `item.wav` - Power-up collection sound
- `bomb.wav` - Explosion sound

## Controls

### Player 1 (Arduino)
- **Directional inputs**: Movement
- **Bomb button**: Place bomb

- ### Player 2 (Arduino)
- **Directional inputs**: Movement
- **Bomb button**: Place bomb
- 
### Player 1 (Keyboard)
- **W/A/S/D keys**: Movement
- **F**: Place bomb

### Player 2 (Keyboard)
- **Arrow keys**: Movement
- **Enter**: Place bomb

## Arduino Serial Protocol

The Arduino should send the following commands via serial:
```
UP_PRESS / UP_RELEASE
DOWN_PRESS / DOWN_RELEASE
LEFT_PRESS / LEFT_RELEASE
RIGHT_PRESS / RIGHT_RELEASE
BOMB_PRESS
```

## Game Mechanics

- **Bomb Timer**: 3 seconds before explosion
- **Bomb Limit**: 3 active bombs per player
- **Starting Stats**: Speed 2.0, Bomb Power 1
- **Grid System**: 40px tiles on 800x600 canvas
- **Victory Condition**: Eliminate opponent with bomb explosion
- **Safe Spawn**: 3-tile radius around starting positions remains clear

![boom](https://github.com/user-attachments/assets/0727f4e9-8ef4-49c5-857a-a9a8fe118289)

## Setup Instructions

1. Install required Processing libraries
2. Connect Arduino and note the serial port (adjust `Serial.list()[1]` in code if needed)
3. Place all assets in the sketch folder
4. Upload appropriate code to Arduino
5. Run the Processing sketch
6. Click "Start" to begin playing

## Development Notes

- Built using Processing 3.x/4.x
- Serial communication at 115200 baud
- 60 FPS gameplay
- Implements collision detection, explosion propagation, and item spawning algorithms
- Procedural map generation avoids player spawn areas

## Course Information

**Course**: Wearables and Nearables  
**Semester**: Fall 2024  
**Institution**: University of Illinois Chicago (UIC)

## Future Enhancements

- Additional power-up types
- More players/game modes
- Online multiplayer
- Level editor
- Mobile controller support

![win](https://github.com/user-attachments/assets/204ceb13-1000-482c-9b8a-965d8e65b243)
