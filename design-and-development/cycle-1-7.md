# Cycle 8: Adding Another Level

##

## Design

### Objectives



* [x] Adding another level
* [x] player should be able to access this level through the portal

### Usability Features

&#x20; the player can go to the next level and play in a  environment that is harder then level 1&#x20;

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
  scene("game", ({ levelId, coins } = { levelId: 0, coins: 0 })	
  if the player touchs the exit ("exit", () => {
		if (incrase by one level ) {
			player the game on the next level", {
		  
			coins: 0
			})
		} else {
		 show win scene
		}
	})

```

## Development

### Outcome

As I have already created a successful first level I did not want to change the design of the second level too much this due to two reasons: with one being that it takes up too much valuable time that can be spent adding additional features as well as refining the game to improve it, and the second reason is I want the player to still be familiar with the levels and have to same objective which is to find and get to the exit. However it does not mean that there has been no alteration as it kept the same design as previous platforms have been added as well as taken away which would make the player find new creative way to get to the exit. In terms of adding platforms, and the addition of moving platforms as well as an acid bath which can instantly damage the player. This is all in   conjunction with the use of more coins for the player to collect through out the level. Finally, the change in the location of the portal to keep the player more engaged as the player would already know the location of the previous portal they have to spend time in order to complete the level. To save time for me to code the game , I have designed the  level in a way that I can use the variable and component of the previous level (talked about in Cycle 1 : Setup)&#x20;

```javascript
 // this is the design for the second level in the game  
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

To complete this cycle the player should be able to go from one level to another level seamlessly. This was achieved by use the variable called levelId in which each level was assigned an id ( a number ) .Once that was done i proceed to use a if statement in which that if the player collides with a portal the game will find the current level that player is on , by using the assigned levelID then increment the levelID by 1 and then take the player to the new level that has the matching levelID. If the player reaches the last level and goes through the portal the function go("win") was used to lead the player to the win scene, to signify that the game has finished and they have won .

<pre class="language-javascript"><code class="lang-javascript"><strong> // this is the code that enables the game to take the player to the next level 
</strong><strong>   scene("game", ({ levelId, coins } = { levelId: 0, coins: 0 })	
</strong>  player.onCollide("exit", () => {
		if (levelId + 1 &#x3C; LEVELS.length) {
			go("game", {
				levelId: levelId + 1,
				coins: coins,
			})
		} else {
			go("win")
		}
	})
</code></pre>

### Challenges

There were no  challenges i faced when adding the additional level to the game.

## Testing

Evidence for testing

### Tests

| Test | Instructions                   | What I expect                                                                                 | What actually happens | Pass/Fail |
| ---- | ------------------------------ | --------------------------------------------------------------------------------------------- | --------------------- | --------- |
| 1    | run code                       | when the player runs the code the should be able to get to the exit with any errors           | runs as expected      | pass      |
| 2    | portal test between two levels | when the player gets to the exit/ portal the portal should take the player to the exit level  | runs as expected      | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>
