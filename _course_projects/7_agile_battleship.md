---
title: "Battleship: Agile Object-Oriented Software Development Project"
excerpt: "This project implements a Battleship game using Agile methodology and JavaFX, featuring multiplayer and AI modes, MVC architecture, and multiple design patterns including Observer and Singleton."
collection: research_projects
permalink: /publication/2026-04-08-battleship-agile-project
share: false
related: false
---

## Problem Statement & Motivation

This project was developed as part of the **Agile Object-Oriented Software Development course at DTU**.

The objective was to design and implement a fully functional **Battleship game**, where two players place ships on a grid and attempt to sink each other's fleet through strategic attacks.

Key challenges included:

- Designing a **modular and scalable architecture**
- Supporting both **multiplayer and AI-based gameplay**
- Implementing **real-time GUI interactions**
- Applying **Agile development practices**

The project emphasizes clean software design, iterative development, and extensibility through design patterns.


## Agile Development Process

The project was developed using **Agile methodology**, focusing on:

- User stories  
- Iterative development cycles  
- Continuous integration of features  
- Team collaboration across roles  

This allowed progressive refinement of gameplay mechanics and system architecture.


## System Design

### Architecture Overview

The system is structured into three main packages:

- `battleship.game` → Core game logic  
- `battleship.gui` → Graphical user interface (JavaFX)  
- `battleship.controller` → Input handling and game coordination  

A root `battleship` package contains the application entry point.

This separation follows the **Model–View–Controller (MVC) architecture**, ensuring clear separation of concerns.


### Key Components

#### Game Logic (`battleship.game`)
Includes:

- Board representation with grid-based cells  
- Player abstraction (Human + AI)  
- Ship placement and lifecycle  
- Game state management  
- AI strategies (Easy and Hard modes)  

Core idea:
→ Encapsulate all game rules independently from the UI.


#### Controller (`battleship.controller`)

Handles interaction between UI and logic:

- `GameController` → central communication hub  
- `GameCreationListener` → event-based game initialization  
- `SoundManager` → audio effects using JavaFX MediaPlayer  

This layer ensures **decoupled input handling and game execution**.


#### GUI (`battleship.gui`)

Responsible for rendering and user interaction:

- Custom JavaFX components (`BattleShipButton`, `GraphicalCell`)  
- Scene management and menu navigation  
- Player boards and game state visualization  
- Real-time updates via observer pattern  

Key feature:
→ Fully interactive graphical gameplay interface.


## Design Patterns

### Singleton Pattern

Applied to:

- `Game`
- `GraphicalGame`

Ensures only one instance exists during runtime:

→ Prevents conflicting game states  
→ Centralizes game management  


### Observer Pattern

Used for event-driven communication:

- **CellListener** → updates GUI when game state changes  
- **PlayerListener** → tracks remaining ships  
- **GameCreationListener** → triggers game initialization  

This ensures **loose coupling between logic and UI**.


### MVC Pattern

- **Model** → `battleship.game`
- **View** → `battleship.gui`
- **Controller** → `battleship.controller`

This separation improves:

- Maintainability  
- Scalability  
- Code clarity  


## Game Features

### Core Gameplay

- Grid-based Battleship mechanics  
- Turn-based shooting system  
- Ship placement with orientation rules  
- Win condition: sink all opponent ships  


### Special Mechanics

- Random **rocks** on the board  
- **Bomb bonus system** when hitting rocks  
- Progress tracking for sunk ships  
- Sound effects and animations  


### Game Modes

- Multiplayer (classic turn-based mode)  
- Blitz Multiplayer (5-second turn limit)  
- Easy AI Bot  
- Hard AI Bot  


## Key Results

- Fully functional Battleship game with GUI  
- Robust AI with two difficulty levels  
- Clean separation of logic using MVC  
- Event-driven architecture using Observer pattern  
- Enhanced gameplay with bonus mechanics (rocks, bombs, timer mode)  


## Contributions

- Designed full **game architecture (MVC-based)**  
- Implemented **core game logic and rules engine**  
- Developed **AI player strategies (easy & hard modes)**  
- Built **JavaFX graphical interface and interactions**  
- Integrated **Observer + Singleton design patterns**  
- Added **bonus gameplay mechanics and sound system**  


## Project Management

### Work Distribution

- Model layer → Entire team  
- Controller → Entire team  
- GUI → Aziz, Mohamed, Thibaud  
- AI Development → Ghalia, Ons  
- Bonus features → Aziz, Mohamed, Thibaud  
- Report → Entire team  

- **Report**: [Full Report](/files/Battleship_Report.pdf)
- **Screencast**: [Youtube](https://youtu.be/fMEB7YwzuNY  )

---

## Implemented Features (Bonus)

- Game menu with sound effects and animations  
- Timed gameplay mode (Blitz mode)  
- Rock obstacles affecting gameplay  
- Bomb mechanics with area-of-effect attacks  
- In-game UI with progress tracking and ship status display  


## Defense & Supervision

- **Institution**: DTU – Agile Object-Oriented Software Development Course  
- **Team Members**: 5 students  
- **Project Type**: Agile software engineering project  
