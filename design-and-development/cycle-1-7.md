# Cycle 7 adding another level

##

## Design

### Objectives



* [x] Adding another level



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |
|               |     |

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

As i have already creted a fisrt sucessful first level i did not want to change the deisgn of the secon level too much this due to two reasons , with one being that it take up much valuable time that can be spend adding addtioal feature as well as refindin the game to better , and the second reason is i want the player to still be familar with the levels and have to same objetvi which is to find and get to the exit. However it does not mean that there has been no alteration for whilst keept the same desgin as the pervious platforms have been added as well as takenaway which would make the player find new creted way to get to the exit. In terms of adding platfrom is the  addtiaion of moving platforms as well as acid bath which can instanly damge the player. this is all in   conjustion with the use of more coins for the player to collect through out the level. finally the the change in the locaiton of the potal to keep the player more engaged as the player would already know the locaiton of the perious portal they have to spend time in oder to comeple the level. To save time  for me to code the game and for the bower to execute the code, i have the desgined  level in a way that i can use the vaible and comppent of the perious level ( talked about in set up cycle 1 )&#x20;

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



```javascript
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
