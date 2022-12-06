# cycle 8 death and falling

##

## Design

### Objectives

For the objective of this cycle, I aim to incorporate a falling death to the game. The way I want this to be implemented is that when the player falls off the level (outside the playable area) or falls from a significant height in the level it will result in the immediate death of the player which makes the player restart the level.

Additionally, the second aim that I have for this cycle is to add a death scene to the game. The way I see the death scene to function within the game is when the player collides with a danger's object within the game (for example, spikes) falling from a height, as previously mentioned, the death scene should appear on the player's screen with one showing to the player that they have died and secondly giving the player the option to go back to the main menu and start again.  &#x20;





* [x] Add falling death   &#x20;
* [x] Add a death scene&#x20;
* [x] &#x20;retunr to start menu



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |
|               |     |

### Pseudocode

```
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

The outcome of both of the objectives was a success as both objectives met all of the requirements that I set out for them at the start of the cycle. &#x20;

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

```javascript
// falling death 
 	player.onUpdate(() => {
		if (player.pos.y >= 2000) {
			go("lose")
		}
	})
```

```javascript
  
 scene("lose", (time) => {
  add([
    text("you have died  ", { size: 24 }),
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


  onKeyRelease("enter", () => {
    go("start");
  })
  
});
```

<figure><img src="../.gitbook/assets/image (1) (1) (3).png" alt=""><figcaption></figcaption></figure>
