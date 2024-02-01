### Course Project Overview

#### Game Idea

The game is based on two AI clients competing to complete a task on a shared map, managed by a server in a client/server setup. Initially, a human starts a game, and then AIs take over, exchanging map halves to create the playing field. Each AI seeks to find its hidden treasure and the opponent's castle on the map, with the first to do so winning the game.

Gameplay is automated, with AIs moving their avatars, uncovering the map, and strategizing to achieve their goals efficiently. The server updates game data, including visible and hidden elements like terrains, treasures, and castles.

The game is turn-based with a maximum of 320 actions or 10 minutes. Non-compliance with rules or unsuccessful navigation results in a loss. The map is collaboratively generated by the AIs, with terrain types and movement rules influencing strategy. The game's progress and outcomes are visualized for spectators through a command-line interface.

The progression of the course project was methodically organized into three main phases, each representing different aspects in developement:

#### **Phase 1: Conceptualization & Architectural Design**

- **Exploration and understanding of the project's scope**, analyzing the game requirements to ensure a clear understanding of what needs to be achieved.
- **Create a detailed documentation of the requirements**, which includes specifying 3 functional and 3 non-functional requirements, as well as outlining a key design choice and business rules to guide me trough the development process.
- **Reviewed existing network protocols**, with a special focus on XML message formats, to ensure compatibility and efficiency in data interchange between client and server.
- **Developed architectural plans for both client and server components**, creating comprehensive class and sequence diagrams to visually represent the system's structure and interaction flows.

#### **Phase 2: Client Side Development**

- **Launched the client development phase**, using an online server provided by the teacher for testing all different requirements and the performance of our AI in different games (unique games).
  - **Implemented a Command Line Interface (CLI)** to see the different stages the game is in like for e.g. generating phase, treasure finding phase, enemy base search phase as well as to provide a visual representation of the games map player moves. 

  ![416000890_864700935654987_2198489879840244406_n](https://github.com/goge1221/Client-Server-Project/assets/75140192/1ec149b5-ca20-4a9f-9cfc-ae58f26536d7)

  Example of game map


- **Integrated RESTful communication protocols**, for the sending and receiving of the map and players moves as well as game statuses, in combination with a Converter that translates the received messages into internal used structures.
- **Formulated an algorithm for generating valid game maps** that meet different criterias such as terrain diversity, ensuring that each game map is unique and meets the game's requirements. The map was in fact a 2D game map using different coodrinates for all the fields.
- **Adopted the Model-View-Controller (MVC) design pattern** for better code organization and maintenance, separating concerns to enhance the scalability and maintainability of the codebase, the MVC pattern was used to update the Map automatically and take decisions based on the informations stored.
- **Developed an AI capable of navigation**, which was divided in two main parts: treasure finder and enemy castle finder, taking decisions based on the phase the player is currently in.
- **Established a detailed logging system** for effective monitoring and debugging, allowing for the tracking of the application's behavior and the identification of issues using the SLF4J library.
- **Implemented robust exception handling mechanisms** for both expected and unexpected scenarios (checked and unchecked exceptions), ensuring that the application can handle errors and continue to operate smoothly.
- **Created a comprehensive suite of unit tests**, including parameterized, negative, and mock tests, to ensure the reliability and quality of the code.

<img width="1440" alt="Bildschirmfoto 2024-02-01 um 16 45 11" src="https://github.com/goge1221/Client-Server-Project/assets/75140192/ec230b20-bd5b-44df-a992-17ca81d43232">

#### **Phase 3: Server Side Development**

- **Initiated server development with the primary goal of enforcing key business rules**, focusing on the implementation of the core logic and validation mechanisms to ensure players are playing according to predefined rules.
- **Designed the server infrastructure to accommodate up to 999 concurrent game sessions**, emphasizing scalability and performance optimization to handle a high number of simultaneous or stability.
- **Integrated RESTful communication protocols**, for sending and receiving of informations about the current game state as telling the players who has to act/wait or who lost/won.
- **Exception handling mechanisms** for evaluating if the player broke rules and for ensuring an enhanced separation of responsabilities, implemented a base exception class from which different game rules inherit. If one of them was broken, report back to players and inform them what went wrong.

### Key takeaways and technologies used

- **Used Spring Boot for easy communication and REST services**, making it simpler to talk between clients and the server, and to exchange data smoothly.
- **Chose SLF4J for logging**, making it easier to keep track of what's happening in the application, help with fixing issues, and ensure it works well no matter where it's run.
- **Made unit tests with mocking and handling exceptions**, to make sure the code is strong and works right even when unexpected things happen, by testing different situations.
- **Set up the server to handle many games at once**, planning the system to let lots of games happen at the same time without slowing down or having problems.
- **Used converters to keep client compatibility even if network talk changes**, making sure the client and server can still understand each other even if the way they communicate changes.
- **Created two game plans for finding treasure and castles, and a way to find the best path to the other player's side**, giving players different ways to try to win and making the game more interesting.
- **Built a simple AI that uses Breadth First Search to look around the map and figure out safe paths without going into water**, making the AI smarter in how it moves and plans its moves on the game map.




