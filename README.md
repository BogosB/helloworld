## LDTS Turma 5 Grupo 04  -  PROJECT HERO

In this project, our goal is to create a text-based RPG game. In the context of this RPG, the player will navigate through a dynamic environment filled with challenges. In this environment, the player will have access to a variety of weapons, each with its own respective stats, which will be used to face different types of enemies. Enemies will have variable stats and strategies depending on their type. Each weapon and monster will have a damage stat, and both the player and monsters will have life stats that can be reduced based on the damage received. Throughout the game, the player must decide on the best strategy to complete the journey, facing monsters and taking care not to deplete their life stat entirely, resulting in a game loss.
In addition to enemies, the player will encounter other challenges such as collecting coins available on the map and navigating around static objects on the path, such as walls and trees. 
The ultimate goal of the game is to progress through the course while enhancing your character, allowing you to eventually confront the final enemy and consequently complete the game.

### AUTORS
This project was developed by the following students: 
 - Bogos Bedik Chaves Sismanoglu (up2022013890)
 - Bruno Coutinho Pereira (up202206351)
 - Tiago Fernando da Costa Ferreira (up 202207311)

### IMPLEMENTED FEATURES
**Player Movement:**
The player character (Player class) is a movable object that can be created at a specific position on the grid.
The player can move in four directions: up, down, left, and right.


  <img src=https://github.com/BogosB/helloworld/assets/64612527/7e03181c-04e1-4067-8627-d6d5ad205477 width="500" height="500">


**Graphics and Printing:**
The game has a graphical user interface (GUI) implemented using the Lanterna library.
There is a “Printer” class responsible for printing both movable and static objects on the screen.

**Game Initialization:**
The game initializes a GUI, a move object, a printer, and various object factories in the GameRun class.
It creates a player, adds it to the movable list, and prints the initial state.

**Object Factories:**
Object factories (GameObjectFactory, MovableObjectFactory, NonMovableObjectFactory, StaticObjectFactory) are used for creating instances of different types of game objects with specific graphics and positions.

**Static Objects:**
There are static objects (e.g., StaticObject, BasicTree, Wall) that can be created at specific positions on the grid with distinct graphics.

### PLANNED FEATURES

Here are the features to be implemented:
- Menu for the player
- More types of enemies and their respective strategies
- Implementation of more varieties of weapons
- Sprite animations
- More map designs

- [GameObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/GameObjectFactory.java)
- [MovableObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/MovableObjectFactory.java)
- [NonMovableObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/NonMovableObjectFactory.java)
- [StaticObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/StaticObjectFactory.java)
- [Gui] https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/GUI
- [Gird] https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/Global/Grid
- [Object] https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/Global/Object
- [StaticObjects] https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/StaticObjects
- [Wepons] https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/Weapons
- [GameRun] https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/GameRun.java
