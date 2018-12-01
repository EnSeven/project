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



