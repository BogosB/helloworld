## LDTS Turma 5 Grupo 04  -  PROJECT RPG

In this project, our goal is to create a text-based RPG game. In the context of this RPG, the player will navigate through a dynamic environment filled with challenges. In this environment, the player will have access to a variety of weapons, each with its own respective stats, which will be used to face different types of enemies. Enemies will have variable stats and strategies depending on their type. Each weapon and monster will have a damage stat, and both the player and monsters will have life stats that can be reduced based on the damage received. Throughout the game, the player must decide on the best strategy to complete the journey, facing monsters and taking care not to deplete their life stat entirely, resulting in a game loss.
In addition to enemies, the player will encounter other challenges such as collecting coins available on the map and navigating around static objects on the path, such as walls and trees. 

The ultimate goal of the game is to progress through the course while enhancing your character, allowing you to eventually confront the final enemy and consequently complete the game.

### AUTORS
This project was developed by the following students: 
 - Bogos Bedik Chaves Sismanoglu (up202201389)
 - Bruno Coutinho Pereira (up202206351)
 - Tiago Fernando da Costa Ferreira (up 202207311)

### IMPLEMENTED FEATURES
**Player Movement:**
The player character (Player class) is a movable object that can be created at a specific position on the grid.
The player can move, using the input reader, in four directions: up, down, left, and right.

<img src=https://github.com/FEUP-LDTS-2023/project-l05gr04/assets/64612527/2c2545ff-8d75-4dbb-b742-8ce2741da506 width="500" height="500">

**Graphics and Printing:**
The game has a graphical user interface (GUI) implemented using the Lanterna library.
There is a “Printer” class responsible for printing game objects on the screen.

**Object Factories:**
Object factories, such as GameObjectFactory, MovableObjectFactory, NonMovableObjectFactory, and StaticObjectFactory, serve the purpose of creating diverse instances of game objects. In the context of this game, a "Game Object" is a foundational element, embodying an entity positioned within a grid-based environment. It is characterized by a specific location, visual representation (symbol and color), and serves as a building block for the game world.

Distinguishing between various types of game objects:

* Static Object:
  Represents an entity that remains fixed and unmovable in the game world.
  Examples include walls, which cannot be traversed or removed by conventional means, requiring the player to transition to another map.

* Non-Movable Object:
  Represents an entity that is stationary but can be interacted with or removed from the map.
  Examples are weapon objects that can be picked up by the player, enhancing their abilities.

* Movable Object:
  Represents an entity capable of both movement and removal from the map.
  Examples include monsters that roam around the map and can be eliminated by the player.

<img src=https://github.com/FEUP-LDTS-2023/project-l05gr04/assets/64612527/065ce2d4-5e2b-4a7a-82c6-e4bf61137820  width="500" height="500">


**Game Initialization:**
The game initializes a GUI, a move object, a printer, and various object factories in the GameRun class.
It creates a player using the factory, reads every input, and then prints the grid occupation class objects

**Monster Activity:**
Every monster has an idle and attacking modes and a strategy, during idle mode every monster roams around the map using its strategy, and when certain conditions are met, the monster enter the attacking mode trying to approach the player.

**Inventory:**
The player has an inventory that stores the weapons that player gathered, and an option to the player choose the current weapon.

**Weapons:**
Many weapons with different types and status (ex:sword, bow, warhammer), were implemented. This weppons are scattered around the map, so that can be collected by the player.

**Phases:**
Different types of maps were created, each map can have weapons and equipments, enemies, static objects and entry/exit points.

**Coins**
Every map has coins that serve as collectibles or as currency to use in stores(if implemented).

**Health**
The game features an HP bar that reflects the current health status of the player.

**Final Game** 
The following gif ilustrate the general look of our game.
<img src:https://github.com/BogosB/helloworld/assets/64612527/d7584616-faed-4c21-a74d-ea0f10cbc01c width="500" height="500>



### PLANNED FEATURES

**Store**
If stores are implemented, they are going to sell weapons and equipments for a price.

**Equipment:**
Not sure if it's going to be implemented, but the idea is to like weapons have many equipments scattered around the map, that are going to work as boosters to player attributes (ex: equipments that modify player speed, health, attack modifier...).


### DESIGN

**Implementation**

The following figure shows how the pattern’s roles were mapped to the application classes:

![uml2 00](https://github.com/FEUP-LDTS-2023/project-l05gr04/assets/64612527/97fbb04c-a604-40b6-9dfd-a460ba168926)

These classes can be found in the following files:

- [staticObjects](https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/StaticObjects)
- [Entities](https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/Entities)
- [Gui](https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/GUI)
- [Gird](https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/Global/Grid)
- [Object](https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/Global/Object)
- [StaticObjects](https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/StaticObjects)
- [Weapons](https://github.com/FEUP-LDTS-2023/project-l05gr04/tree/dev/src/main/java/com/projects/ldtsProject/Weapons)
- [GameRun](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/GameRun.java)




#### HANDLING DIFFERENT TYPES OF GAME OBJECTS

**Problem in Context**

In the game design, there was a need to handle different types of game objects, each with its own behavior, such as movable objects, non-movable objects, and static objects. The initial idea involved creating individual classes for each type of object, leading to too many similar classes that couldn't share identical methods and similar constructors between them. This could be better organized in a way that every game object instance is a game object subclass.

**The Pattern**

Even thought the design may preset more than one pattern partial implementation, to address the problem, we applied mainly the Composite Pattern. This pattern allows you to treat individual objects and compositions of objects uniformly through a common interface. It helps in creating a tree structure where leaf nodes (individual objects) and composite nodes (compositions of objects) share the same interface.

**Implementation**

The following figure shows how the pattern's roles were mapped to the application classes.

![GameObject](https://github.com/FEUP-LDTS-2023/project-l05gr04/assets/64612527/cb260105-2975-40eb-ab90-45f0df24fab8)


These classes can be found in the following files:

- [GameObject](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/GameObject.java)
- [MovableObject](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/MovableObject.java)
- [NonMovableObject](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/NonMovableObject.java)
- [StaticObject](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/StaticObject.java)

**Consequences**

* Benefits:

The Composite Pattern provides a unified interface (GameObject) for all types of game objects, promoting consistency.
New types of game objects can be added without modifying existing code, adhering to the Open/Closed Principle.
Code related to the interaction with game objects is more modular and follows the Single Responsibility Principle.
By applying the Composite Pattern, the design becomes more flexible, modular, and adherent to established design principles. It allows for easy extension to handle new types of game objects without disrupting existing functionality.

* Liabilities:

The introduction of the Composite Pattern increases the number of classes and instances, which might be perceived as a slight increase in complexity.
Constructors may get more complex due to having to give as argument some shared attributes, that may not be used in all subclasses




#### CREATING NEW GAME OBJECTS BECOMING TOO REDUNDANT

**Problem in Context**

Due to the growing complexity of making new game objects, like for creating a new monster the constructor needed (int posX, int posY, String ch, String color TextGraphics textGraphics, MoveObject moveManager, CollisionDetector collisionDetector), but the problem was that (TextGraphics textGraphics, MoveObject moveManager, CollisionDetector collisionDetector) are shared among all monsters, and (String ch, String color) are defined in the monster class there was a need to create a method that creates that same monster only using the (int posX, int posY, object type), which is much more easier and less redundant.

**The Pattern**

Here the main pattern was the factory, since the shared attributes could be used in the factory constructor, which don't need to be used as many times and then add a new method to the factory that only takes the individual attributes.

**Implementation**

The following UML class diagram illustrates how the Factory Pattern was implemented:

![GameObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/assets/64612527/0bcfd965-b6b0-4fca-aa84-dec6ee5aa6d3)


These classes can be found in the following files:

- [GameObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/GameObjectFactory.java)
- [MovableObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/MovableObjectFactory.java)
- [NonMovableObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/NonMovableObjectFactory.java)
- [StaticObjectFactory](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Object/StaticObjectFactory.java)

**Consequences**

* Benefits:
Now it's much easier to build new objects and the classes hierarchy is maintained (ex: Player object can be built as GameObject or MovableObject).
If we need to add another shared attribute among game objects, we now only need to make changes on factories methods and constructors.
New types of game objects can be added without modifying existing code, adhering to the Open/Closed Principle.

* Liabilities:
The introduction of factories adds a layer of abstraction, which may be perceived as a slight increase in complexity.





#### GLOBAL CLASS NEEDED FOR GRID OCCUPATION

**Problem in Context**
Because grid occupation class needs to work as a global class, to be easier to access it and modify it, there's some precautions that we needed to take, like guaranteeing that we have only one instance of that class running, and that it's possible to get that class as an attribute without necessarily using its instance on the constructor.

**The Pattern**
The pattern we decided to use was the singleton, because it auto initializes the class, guarantees only one instance using the private constructor and have a method capable of returning that instance that can be used in any other part of the code.

**Implementation**

The following UML class diagram illustrates how the Factory Pattern was implemented:

![GridOccupation](https://github.com/FEUP-LDTS-2023/project-l05gr04/assets/64612527/a8f0e96e-71bb-45e5-8c68-86de5cad94e1)

These classes can be found in the following files:

- [GridOccupation](https://github.com/FEUP-LDTS-2023/project-l05gr04/blob/dev/src/main/java/com/projects/ldtsProject/Global/Grid/GridOccupation.java)

**Consequences**

* Benefits:
It's possible to access grid occupation methods in every class.
It's possible to work with only one global list of game objects, which makes things like print and detect collisions easier.

* Liabilities:
In case we need one more instance of grid occupation, a great part of code is going to need a revamp.
In case we work with multi-threading, if not well synchronized, there can be error due to multiple threads trying to access the same global list.
Makes testing every class that implements grid occupation harder.

### Testing
![image](https://github.com/FEUP-LDTS-2023/project-l05gr04/assets/38361094/5f65678b-1291-43b6-8efc-920630a672c2)


### Self-Evaluation

**Bogos:** Did the UMLs and worked on the README.

**Bruno:** Did the code and worked on the README.

**Tiago:** Did the tests and the mockup.
