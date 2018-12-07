# Word Wizard

## an EnSeven production
*EnSeven is a student organization*

#### CLIENT: Ashley Breunich, Mike Kermes, Brandon Hayes, Nicholas Welch
#### GAME ENGINE: Chris Kozlowski, Hollie Thomas, Matthew McQuain, James McDaniel
#### API: Kevin O'Halloran, Ed Puzino, Hai Le, James Denton

## Purpose

The purpose of this project is to illistrate our cumulative knowledge of backend web development through the example of a game, consisting of a custom built API, a client server and a game made with socket.io.  

## Playing the Game

In order to play Word Wizard, users will need to fork the client repo and clone it down to their machine. They can use [this](https://github.com/EnSeven/client) link to access the repository. 

1. Once the repository is on the computer, users will then need to install all dependencies (by typing `npm install` into terminal) 

2. In order to start a game, a player will need to type `nodemon` OR `node client.js` into terminal. Users will then be connected to the game server and will be prompted to either CREATE an account or LOGIN to an existing account. 

## Functionality between Client and Game-Engine

The client.js file is a Socket.IO server that connects to the game server's [Heroku link](https://enseven-game-engine.herokuapp.com). Upon starting up the client in the terminal (nodemon OR node client.js), a user will be connected to the game server and prompted to either CREATE a new account or LOGIN to an existing account. These prompts are initiated by both Readline and the npm package Prompt, which, based on a schema, prompt the user for their email (must be unique), username (must be unique), and password. See documentation links in Citations section below. 

Once a token is sent back from the API to the game server, the game server notifies the client server. Upon receipt of notification the user is signed in and able to request to join the game. Once two players join the game, they begin playing, alternating turns guessing letters until they either run out of turns or guess the correct word. They are alerted if they won the game or lost the game and their stats are stored for future use. 

## Functionality between Game-Engine and API 

Game-Engine is a Socket.IO server that connects to both Client server and the API. Once a user has selected to either create or login as an exsisiting user, Game-Engine sends the user data; username, password, and email to the API. The API sends back a token using JWOT. The token is an authenticator for data transfers between Game-Engine and API.

## API functionality

The API is a database for storing users information and is protected from client access. The API stores individual game results and keeps tracks of player statistics including wins/losses. 





## Citations
[Socket.IO Documentation](https://socket.io/docs/)

[Chalk Documentation](https://www.npmjs.com/package/chalk)

[Prompt Documentation](https://www.npmjs.com/package/prompt)

[Readline Documentation](https://nodejs.org/api/readline.html)

EnSeven uses [Socket.IO](https://socket.io/docs/) to connect two players to a game of hangman played directly from their terminal windows. A user can either create a new account or log into an existing account upon connection to the game server. Their wins and losses will be kept track of every time they complete a game. 

## 12/01 Developer Stories

**Client Side**

- As a developer, I will work on a staging branch. 

- As a developer, I will work with the API team to validate the password, including all catch-all scenarios of incorrect inputs, wrong password, etc.

- Stretch Goal: Testing

- Monday: As a developer, I want to work on the input stream for the game. I will need to pass the request for users stats to the API team. 

**GAME ENGINE**

- As a developer, I will work on a staging branch.

- As a developer, while I wait for other teams to complete in order to move forward, I will begin testing. 

- As a developer I want to work with Server/API team to standardize the socket.io emits or “payload” and how to manage the token.

- I will work with a representative from the Server/API team and pair program. 

- Stretch Goal: Wiki entry

**SERVER/API**

- As a developer, I will work on a staging branch.

- As developers, I will utilize pair programing with both my team and the Game Engine team.

- As a developer, I will need to receive the request for user stats and send it to the Client side team.

- As a developer, I will integrate Bearer Authorization. 

- Stretch Goal: Testing, TravisCI 

**USER STORIES**

- As a user I would like to know how to play the game when I log in.

- As a user I would like to be able to type in a command, listed in the “how to play” message, to see a list of all game commands.

- As a user I would like to enter a command to see my game stats.

- As a user I would like to enter a command to see a leaderboard of the top 10 players.

- As a user, if i am required to use my email to log in, I would like to create a username that is not my email log in.

- As a user I would like to know when a game will start i.e. “waiting for 2nd player to join”

- Stretch goals:

- As a user I would like to connect to a home room when I log in where I can choose to join next available game or create a private room to play against a friend.

- As a user I would like a chat function with other connected players.
