# Chinese Whispers

A childhood game, played with chained microservices. 

There is a central _Games Master_ interface that "players" will check-in with. Each player is an interface to a microservice/scraper that conforms to provide the same route-response pattern. The Games Master will maintain a "circle" of players and when a game is played each player will be hit in turn 1-by-1, with the result of the previous player being handed to the next, until every player has had a go and the game is complete. The end result is a story of how one phrase became another. 

It is similar to a couple of popular games: [The Chain](https://www.thechain.uk/) on BBC6Music and [6 Degrees of Separation/Kevin Bacon](https://en.wikipedia.org/wiki/Six_degrees_of_separation).

## Games Master

HTML + JavaScript interface for controlling the games. A form will take input to trigger the start of a new game. Text elements below will output a live feed as a game is played and show the result. 

## Players

Players must explose an end-point that receives a GET request that accepts a single parameter called `hear`
eg. example.com/jons?hear=Lovely%20biscuit

It must return a JSON response that includes the following 3 key-pair values:
 - `heard` - The phrase exactly as it was passed to the player _(eg. 'Lovely biscuit')_.
 - `said` - The new phrase, whispered by the player _(eg. 'Medical emergency')_.
 - `explanation` which describes how the player got there _(eg. 'This word was on the same page as this Wiki page')_.


## Suggested sources
 - twitter
 - facebook
 - instagram 
 - youtube
 - sound cloud
 - Wikipedia page
 - User comments
 - Related news articles
 - TV listings
 - IMDB data

