# Chinese Whispers

A game with chained microservices. 

There is a central _Games Master_ interface that "players" will check-in with. Each player is a microservice that conforms to provide the same route-response pattern. The Games Master will maintain a "circle" of players and when a game is played each player will be hit in turn 1-by-1, until everyone has had a go and then the game is complete. The end result is a story of how one phrase became another. 

## Games Master

HTML interface. Input box to start the game. Text element to contain the output as a game is played. 

## Players

Players must receive a POST request in the following format:
```
{
    hear: 'fdsf'
}
```

And return JSON response that **must** include a 3 key-pair values:
 - `hear` - The phrase from the previous
 - `say` - The new phrase
 - `explanation` which describes how you got there _(eg. This word was on the same page as this Wiki page)_
