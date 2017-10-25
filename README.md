# Chinese Whispers

A game with chained microservices. 

There is a central _Games Master_ interface that "players" will check-in with. Each player is a microservice that conforms to provide the same route-response pattern. The Games Master will maintain a "circle" of players and when a game is played each player will be hit in turn 1-by-1, until everyone has had a go and then the game is complete. The end result is a story of how one phrase became another. 

## Games Master

HTML interface. Input box to start the game. Text element to contain the output as a game is played. 

## Players

Players must receive a POST request that accepts a single parameter called `hear`:
```
{
    hear: 'Lovely biscuit'
}
```

It must return JSON response that **must** include the following 3 key-pair values:
 - `heard` - The phrase exactly as it was passed to the player _(eg. 'Lovely biscuit')_.
 - `said` - The new phrase, whispered by the player _(eg. 'Medical emergency')_.
 - `explanation` which describes how you got there _(eg. 'This word was on the same page as this Wiki page')_.


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

