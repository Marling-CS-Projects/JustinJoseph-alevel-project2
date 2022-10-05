# cycle 8 death and falling

##

## Design

### Objectives

For the objective of this cycle, i aim to incorporate a falling death to the game. The way i see this to be implemented is that when the player falls of the level ( outside the play able area ) or falls from a significant height in the level it will result in the intimidate death of the player which makes the player restart the level .

Additionally , the second aim that i have for this cycle is to add a death scene to the game. The way i see the death scene to function with in the game is when the player collides with a danger's object within the game ( example spikes ) or previously mentioned falling from a height the death scene should appear on the players screen with one showing to the player that they have died  and secondly giving the player the option to go back to the main menu and start again .  &#x20;





* [x] add falling death   &#x20;
* [x] &#x20;add a death scene&#x20;



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

The outcome of the both of the objective was a success as both objectives met all of the requirement that i set out for them at the start of the cycle . &#x20;

### Challenges



## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect | What actually happens | Pass/Fail |
| ---- | ------------ | ------------- | --------------------- | --------- |
| 1    |              |               |                       | Fail      |
| 2    |              |               |                       | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

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
