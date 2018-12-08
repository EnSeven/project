



# Word Wizard **![](https://lh6.googleusercontent.com/GgT9N45K9nwbHLxGFM2Zs5zd6ui34N5TnD7-gZak-WfQWNrKM0iebbTErikHvMiTXm1bLpR8Bv_Q5uLbiEe-WcAuxhaxuQtyRLQJduhyhUEVLvOuoIodXlXpLQkv-LSnFRu_o2P0fVM)**
  ##### an **EnSeven** production

##### *EnSeven is a student organization*

  

#### CLIENT: Ashley Breunich, Mike Kermes, Brandon Hayes, Nicholas Welch

#### GAME ENGINE: Chris Kozlowski, Hollie Thomas, Matthew McQuain, James McDaniel

#### API: Kevin O'Halloran, Ed Puzino, Hai Le, James Denton

  

## Purpose

  

The purpose of this project is to illistrate our cumulative knowledge of backend web development through the example of a game, consisting of a custom built API, a client server and a game made with socket.io.

  

## Playing the Game

  

In order to play Word Wizard, users will need to fork the client repo and clone (`git clone`) it down to their machine. They can use [this](https://github.com/EnSeven/client) link to access the repository.


  

1. Once the repository is on the computer, users will then need to install all dependencies (by typing `npm install` into terminal)

  

2. In order to start a game, a player will need to type `nodemon` OR `node client.js` into terminal. Users will then be connected to the game server and will be prompted to either **CREATE** an account or **LOGIN** to an existing account.

  

## Functionality between Client and Game-Engine

The client.js file is a Socket.IO server that connects to the game server's [Heroku link](https://enseven-game-engine.herokuapp.com). Upon starting up the client in the terminal (`nodemon` OR `node client.js`), a user will be connected to the game server and prompted to either CREATE a new account or LOGIN to an existing account. These prompts are initiated by both Readline and the npm package Prompt, which, based on a schema, prompt the user for their email (must be unique), username (must be unique), and password. See documentation links in Citations section below.
  
Once a token is sent back from the API to the game server, the game server notifies the client server. Upon receipt of notification the user is signed in and able to request to join the game. Once two players join the game, they begin playing, alternating turns guessing letters until they either run out of turns or guess the correct word. They are alerted if they won the game or lost the game and their stats are stored for future use.

  

## Functionality between Game-Engine and API
Game-Engine is a Socket.IO server that connects to both Client server and the API. Once a user has selected to either create or login as an exsisiting user, Game-Engine sends the user data; username, password, and email to the API. The API sends back a token using JWOT. The token is an authenticator for data transfers between Game-Engine and API.

  

## API functionality
The API server provides the interface to the persistence layer, which is implemented using MongoDb. When users sign up, or return to play again, the API is accessed. The game engine uses API services to persist and retrieve information about wins and losses.

  
## Code Samples
  ### Client Server example code {*user connected*}
  ```
 socket.on('start', (payload) => {
    console.log('payload', payload);
    socket.emit('connected', `Player ${socket.id} ready`);
    console.log(`Player ${socket.id} has joined the game`);
  });
  ```
### Socket.io example code {*user disconnected*}
```
  socket.on('disconnect', () => {
    socket.removeAllListeners();
    console.log(`Player ID ${socket.id} has left the game`);
  });
  ```
  ### API example code {*user signs in*}
  ```
  authRouter.post('/signin', auth(), (req, res, next) => {
  res.cookie('auth', req.token);
  res.send(req.token);
});
  ```
  

## Citations

[Express Documentation](https://www.npmjs.com/package/express)
[![npm version](https://badge.fury.io/js/express.svg)](https://badge.fury.io/js/express) 
 
[Chalk Documentation](https://www.npmjs.com/package/chalk)
[![npm version](https://badge.fury.io/js/chalk.svg)](https://badge.fury.io/js/chalk)  

[Prompt Documentation](https://www.npmjs.com/package/prompt)
  [![npm version](https://badge.fury.io/js/prompt.svg)](https://badge.fury.io/js/prompt)

[Readline Documentation](https://nodejs.org/api/readline.html)
[![npm version](https://badge.fury.io/js/readline.svg)](https://badge.fury.io/js/readline)
  
  [Socket.IO Documentation](https://socket.io/docs/)
  [![npm version](https://badge.fury.io/js/socket.io.svg)](https://badge.fury.io/js/socket.io)
