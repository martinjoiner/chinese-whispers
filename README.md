# chinese-whispers

A game with chained microservices.

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



##Suggested methods
 - twitter
 - facebook
 - instagram 
 - youtube
 - sound cloud

