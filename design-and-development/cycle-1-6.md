# Cycle 7: Adding Another Level

##

## Design

### Objectives



* [x] Adding another level
* [x] player should be able to access this level through the portal

### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name                      | Use                                                                                                                                                                                                                            |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <pre><code>go("win")
</code></pre> | this allow the game to switch to the win scene once the player has completed all of the levels                                                                                                                                 |
|  levelID                           | this variable is uses that assign each level with a id  ( a number ) so that when it comes time to go the next the  game can now by incrementing by one know what is the name of the level that the player should be going to  |

### Pseudocode

&#x20;&#x20;

```
',
   '                                                                            ',
   '                                                                             ',
   '                  m              m                           ccc                 ',
   '                                                                             ',
   ' ppp            ppppp        j              ppp                               ',
   '                                                                             ',
   '                                                                             ',
   '                     sccs             cscs                         ccssc           ',
   '      pppp          ppppp           ppppp          a                             ',
   '                                                                             ',
   '                                                                             ',
   '             pppp                                      pppp                          ',
   '                                                                             ',
   '  s                                c  c  c                 pppp                   ',
   ' pppp                            c   @  c                             ',
   '                                  c  c c                                    ',
   '    p                      j                                             p      ',
  '                                                                              ',
   '                cc               ss                  sss                ccc     ',
   '             ppppp             ppppp                ppppp              pppp ',
   '              s                                                               ',
   '                                                                              ',
   '                       cs                   ss                 e                 ',
   '   pppp               pppppp             pppppp              pppppp         ',
   '                                                                              ',
   '                                                                             ',
   '                                                   s                          ',
   '             pppppp                            ppppppp          pppp      ',
   '                            j                                                 ',
   '                             j                                              ',
   '                              j                                               ',
   '                                                                     s   ',
   '============================================================================',
 ]

```

## Development

### Outcome

As I have already created a successful first level I did not want to change the design of the second level too much this due to two reasons: with one being that it takes up too much valuable time that can be spent adding additional features as well as refining the game to improve it, and the second reason is I want the player to still be familiar with the levels and have to same objective which is to find and get to the exit. However it does not mean that there has been no alteration as it kept the same design as previous platforms have been added as well as taken away which would make the player find new creative way to get to the exit. In terms of adding platforms, and the addition of moving platforms as well as an acid bath which can instantly damage the player. This is all in   conjunction with the use of more coins for the player to collect through out the level. Finally, the change in the location of the portal to keep the player more engaged as the player would already know the location of the previous portal they have to spend time in order to complete the level. To save time for me to code the game and for the bower to execute the code, I have designed the  level in a way that I can use the variable and component of the previous level (talked about in Cycle 1: Setup)&#x20;

```javascript
   '                                                                            ',
   '                                                                             ',
   '                  m              m                           ccc                 ',
   '                                                                             ',
   ' ppp            ppppp        j              ppp                               ',
   '                                                                             ',
   '                                                                             ',
   '                     sccs             cscs                         ccssc           ',
   '      pppp          ppppp           ppppp          a                             ',
   '                                                                             ',
   '                                                                             ',
   '             pppp                                      pppp                          ',
   '                                                                             ',
   '  s                                c  c  c                 pppp                   ',
   ' pppp                            c   @  c                             ',
   '                                  c  c c                                    ',
   '    p                      j                                             p      ',
  '                                                                              ',
   '                cc               ss                  sss                ccc     ',
   '             ppppp             ppppp                ppppp              pppp ',
   '              s                                                               ',
   '                                                                              ',
   '                       cs                   ss                 e                 ',
   '   pppp               pppppp             pppppp              pppppp         ',
   '                                                                              ',
   '                                                                             ',
   '                                                   s                          ',
   '             pppppp                            ppppppp          pppp      ',
   '                       m                                                      ',
   '                               m                                              ',
   '                              m                                               ',
   '                                                                     s   ',
   '============================================================================',
 ]
```



For this cycle to considered a success the player should be able to access the next level from within the game (the previous level), which it has. This was done with the following code:&#x20;

```javascript
  scene("game", ({ levelId, coins } = { levelId: 0, coins: 0 })	
  player.onCollide("exit", () => {
		if (levelId + 1 < LEVELS.length) {
			go("game", {
				levelId: levelId + 1,
				coins: coins,
			})
		} else {
			go("win")
		}
	})
```

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect | What actually happens | Pass/Fail |
| ---- | ------------ | ------------- | --------------------- | --------- |
| 1    |              |               |                       | Fail      |
| 2    |              |               |                       | Pass      |

### Evidence
