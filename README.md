# SDL Tower Defense Game

## Engine Summary
This project is built on a custom C++ game engine powered by SDL2. The engine provides:
- **SDL Initialization & Shutdown**: Wraps `SDL_Init`, `IMG_Init`, `TTF_Init` and their corresponding quit calls.  
- **Window & Renderer Abstraction**: Manages `SDL_Window*` and `SDL_Renderer*` creation, configuration, and teardown.  
- **Resource Management**: Loads and caches textures, fonts, and audio assets for efficient reuse.  
- **Input Handling**: Centralizes SDL event polling into an `InputManager` API (key states, mouse, quit events).  
- **Scene Management**: Implements a `Scene` base class and `SceneManager` to push/pop game states cleanly.  
- **Fixed-Timestep Game Loop**: Handles delta-time calculation, update → render → present cycles, and frame limiting.  
- **Clean Modularity**: Public headers in `include/`, implementations in `src/`, and third-party dependencies under `extern/`.

These core systems let you focus on game logic—like tower defense mechanics—without rewriting boilerplate each time.

---

## Games made on this Engine

### Tower Defense
![image](https://github.com/user-attachments/assets/fe61a130-5561-4482-a10a-1425b8c03c32)

### Platformer
![image](https://github.com/user-attachments/assets/4cd8ebd0-7f22-442f-8390-d2ec0590b5e3)

### Breakout
![image](https://github.com/user-attachments/assets/803486d3-dd40-409c-a6bb-1a402ff02545)

---

## 🚀 Project Summary
A custom 2D tower-defense game built on the above minimal C++/SDL2 engine. Place towers, fend off waves of enemies along preset paths, earn currency, and survive as many rounds as you can! The engine’s flexibility also includes a built-in level editor for free-form environment placement.

---

## 🚀 Features

### ✅ Must (Implemented)
- **Enemy Spawning**: Enemies spawn from the start gate each wave.  
- **Pathing**: A single track from entry to exit—the enemy follows a deterministic path.  
- **Basic Tower**: Click to place a tower; it automatically targets and shoots enemies, removing them and awarding currency.  
- **UI Panel**: Left-side HUD shows lives remaining, current currency, and available tower types.  
- **Turn-Based Rounds**: Build phase → “Start” button → attack phase.  
- **Economy & Score**: Earn and spend currency; score updates correctly.  
- **Win/Loss Conditions**: Victory on clearing all waves or reaching target round; defeat on losing all lives. Menus respond appropriately.

### 🚧 Should
- **3+ Tower Types**: Three distinct towers with different mechanics.  
- **3+ Enemy Types**: Three unique enemies with varying speed/health/behavior.

### ⭐ Could
- **3+ Maps**: Three distinct levels/maps to choose from.  
- **Round Display**: Current round and remaining rounds shown on HUD.

### 🚫 Won’t
- Consumable items outside of towers  
- Terrain-specific tower types  

### 🔧 Extensions (Implemented)
- **Targeting Modes**: User can select tower targeting (“Strongest,” “Weakest,” “First,” “Last”).  
- **Enemy Health Bars**: Each enemy displays a health bar above its sprite.  
- **Anti-Tank Mine**: A special mine-style tower with area damage.  
- **Environment Editor**:  
  - Place & delete freeform environment objects (trees, rocks, decorations) in the Level Editor.  
  - Simultaneously edit up to 5 layering files for environment data.

> **Note on Upgrades**  
> We opted not to implement tower upgrades—this was scoped out to keep gameplay balanced and avoid overpowering early waves.

---

## 🎮 Getting Started

### Prerequisites
- **SDL2**, **SDL2_image**, **SDL2_ttf** development libraries  
- A C++11-capable compiler (e.g. `g++` or `clang++`)  

### Build & Run
```bash
# Clone the repo
git clone https://github.com/RecklessHogrider96/SDL-Game-Engine.git
cd SDL-Game-Engine

# On Linux/macOS with Makefile:
make

# Run the game:
./SDLGameEngine
