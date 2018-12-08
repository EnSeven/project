[![Build Status](https://travis-ci.com/EnSeven/apiServices.svg?branch=master)](https://travis-ci.com/EnSeven/apiServices)

# Additional documentation on the Application Program Interface

The API server provides the interface to the persistence layer, which is implemented using MongoDb. When users sign up, or return to play again, the API is accessed. The game engine uses API services to persist and retrieve information about wins and losses.

The Auth layer supports regular authorization (name + password) as well as "bearer auth", which passes an encoded token back to the game engine to use in subsequent writes and reads to and from the API. After signing in with user name and password, the token allows the client to identify the gamer on subsequent requests without requiring the gamer to type in his or her credentials more than once per session. Furthermore, the game engine can use the token on the gamer's behalf as necessary as it writes data or requests data from the API layer.

Get and Post routes are protected by Auth middleware where appropriate. In most cases this middleware checks for expected permissions ("capabilities") as well as authenticating the user's identity, before granting access to the requested service.

The API layer implements a simple Access Control List (ACL) architecture for tracking users and their permissions. Users are assigned a role (typically "gamer"), which has a specific list of privileges (called "capabilities.")

The game client communicates directly only with the game engine. The API communicates directly only with the game engine. Consequently in certain cases, such as signup, the game engine passes along requests from the client to the API and vice versa. In other cases, the game engine is delegated by the client to communicate directly with the API layer as appropriate.


