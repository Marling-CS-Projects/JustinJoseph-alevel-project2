# Cycle 8 death and falling

##

## Design

### Objectives

For the objective of this cycle, I aim to incorporate a falling death to the game. The way I want this to be implemented is that when the player falls off the level (outside the playable area) or falls from a significant height in the level it will result in the immediate death of the player which makes the player restart the level.

Additionally, the second aim that I have for this cycle is to add a death scene to the game. The way I see the death scene to function within the game is when the player collides with a danger's object within the game (for example, spikes) falling from a height, as previously mentioned, the death scene should appear on the player's screen with one showing to the player that they have died and secondly giving the player the option to go back to the main menu and start again.  &#x20;





* [x] Add falling death   &#x20;
* [x] Add a death scene&#x20;
* [x] &#x20;return to start menu



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |
|               |     |

### Pseudocode



```javascript
// falling death 
if player falls below 1000(
 death scene
 )
```

```
if player touches anything dangers'(
  display death scene
  give the option to the player to play again 
  )
```

## Development

### Outcome

The first objective of this cycles was to add a feature to the game in which that if the player fall out  of the game map or falls for too long the game should instantly end it self and give the player the option to start the game again. For this feature to work l used a If statement in which that the game will use the current position of the player in the Y coordinate direction `(player.pos.y)` and compare the value to an const value of 2000 . If the player falls below  the const value the game will end itself thus referring the player to end scene "`go("lose")`".

```javascript
// falling death 
 	player.onUpdate(() => {
		if (player.pos.y >= 2000) {
			go("lose")
		}
	}

```

If a player fails the game they reffered to lose scene other wise i found the game often crashes. To minimalism the time wasted for the player i aim to keep the lose scene simple and easy to use . This meant that i only need a few strings of text , one string of text to for the player acknowledge that the player had lose the game and another string of text to let them know how to restart the level.&#x20;

To do this l create the scene with the variable name  "lose" this is the vaibel name that i would use to when the player dies from coillion with obsclte or the enemy or falling death. Aftere the scene was created i added the two bit of information need fist being the acknowledgement of death whcih was done with the code text("game over  ",  the line of the code { size: 24 }), is used as a sizing tool, by using size of 24 it enable the text to large making it easy for the player ot read. This is in addition to letting the player know how to get to back to main menu.

```javascript
  
 scene("lose", (time) => {
  add([
    text("game over", { size: 24 }),
    pos(vec2(500, 350)),
    origin("center"),
    color(255, 255, 255),
    text
  ]);

  add([
    text("press enter to go back to the start screen ", { size: 24 }),
    pos(vec2(400, 200)),
    origin("center"),
    color(255, 255, 255),
    text
  ]);

});
```

To enable the player to get main menu i have Incorporated a click button via the use of a mouse that will take the player back to the main menu this is done with the command  go("start") with the vaible name start referring the name of the scene .&#x20;

```javascript

  onKeyRelease("enter", () => {
    go("start");
  })
```

### Challenges



## Testing

Evidence for testing

### Tests

| Test | Instructions   | What I expect                                                                                                                           | What actually happens                                                                                                                                                              | Pass/Fail |
| ---- | -------------- | --------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Falling death  | When the player falls outside of the level the player should die and the death screen should show after a certain distance of falling.  | When the player strays too far away from the level, they will die after a short distance.                                                                                          | Fail      |
| 2    | Falling death  | When the player falls outside of the level the player should die and the death screen should show after a certain distance of falling.  | When the player jumps off the level, the player is dead when they go below the base floor of the game as well as that the player will die if they are falling for a long distance. | Pass      |
| 3    | Death scene    | When the player collides with a dangerous object, the death screen should appear.                                                       | When the player dies the death screen appears.                                                                                                                                     | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (1) (1) (3).png" alt=""><figcaption></figcaption></figure>
