# EnSeven

## Client App
- [ ] Connects a game player to the game engine through Socket.IO
- [ ] If logging in, keeps the token and sends back with responses/prompts
- [ ] Receives a prompt from the server
- [ ] Sends a response in
- [ ] Awaits reply / status update

**Team Members**  
- Ashley
- Brandon
- Michael 
- Nick

## Game Engine
- [ ] Awaits gamer connections (offloading login to API)
- [ ] Sends a prompt
- [ ] Receives a response
- [ ] Determines winner
- [ ] Logs outcome (to user account, if logged in)
- [ ] Sends Response

**Team Members**  
- Hollie
- Chris
- Matt
- James McDaniel

## API Services
- [ ] Handles User Login / Authentication on each move
- [ ] Logs Progress
- [ ] Manages levels, earnings, spiffs, etc
- [ ] Connects to the DnD API? 

**Team Members**  
- Hai
- Kevin
- James Denton
- Ed

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
