# Cycle 5: Enemy

##

## Design

In this cycle, I aim to add a bot to my game. The function of this bot is to shoot at the player when they are within line of sight as well as guard gates to the next level. I aim to add different types of bots with different abilities. &#x20;

### Objectives



* [x] Add bots&#x20;
* [x] Make the bots move



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name                    | Use                                                                                                                                                                                          |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre><code> patrol
</code></pre> | This variable is used to store the actions (the command) of the enemy bot which is the movement of the enemy from left to right and what will happen if the player collides with the player. |
| this .move                       | This is the variable used to give the bot the speed and direction to going in left and right.                                                                                                |
|                                  |                                                                                                                                                                                              |

### Pseudocode

<pre><code><strong>function ( speed , dir  ){
</strong>
	return {
		id: "patrol",
		require: [ "pos", "area", ],
		add() {
			when bot toches another object => {
				if (col.isLeft() || col.isRight()) {
					dir = -dir
				}
			})
		},
		update() {
			the bot changes directions 
      
		},
	}
}
</code></pre>

## Development

### Outcome



To start off my development cycle I first created an enemy that the player can see and interact with. This persuaded me to keep my sprite for my enemy simple with the intention of keeping it PEGI 12 as I was very keen to integrate the enemy and make it functional.

![](<../.gitbook/assets/image (10) (4).png>)



Once the drawing for the enemy was created I uploaded it onto kaboom.js and added the image file address to the game code and gave it a tag id of "enemy". This is what is done throughout the development cycle to refer when coding the enemy.

```javascript
loadPedit("enemy", "sprites/enemy.pedit");
```

Once the enemy was added to the game it was needed for the enemy have a purpose in the game.  The function called "patrols" allow the enemy to move around in a set area. Currently, I have set the movement of the enemy only to left and right direction as this is what is needed in my game. This has been achieved with the two lines of code if (col.isLeft() || col.isRight()) { dir = -dir  to allow the enemy to move autonomously. with the subsequent line having the reference to the speed component.



```javascript
function patrol(speed =75 , dir = 1) {

	return {
		id: "patrol",
		require: [ "pos", "area", ],
		add() {
			this.on("collide", (obj, col) => {
				if (col.isLeft() || col.isRight()) {
					dir = -dir
				}
			})
		},
		update() {
			this.move(speed * dir, 0)
      
		},
	}
}
```

With the new feature developed I proceeded to incorporate everything together in a variable function that can be called upon when needed. I used "e" as the function name, within that it contains the enemy sprite image that the player would see when player the game, after which I used the area() to give the enemy a hitbox - this became very useful as it is a way for the game to end itself when the player comes in contact with the enemy (this is done when both player and enemy hitboxes overlap), then after the scale function was used, this is because when the sprite enemy was tested in the game I found it to be too big for the game and its surroundings. By giving it a scale of 3.5 it was within the right proportions to the game. then the new function patrol() was added which allowed the enemy to move in the specified area by itself with a set boundary. Lastly, since the purpose of the enemy is to be an obstacle I used the danger tag and catergorised it as such. By using the categorisation it has made the coding process more efficient due to the fact anything that falls under the danger tag means that the game will end itself and the lose scene will appear if the player comes in contact with it.&#x20;

```javascript

  "e": () => [
    sprite("enemy"),
    area(),
    origin("bot"),
    body(),
    scale(3.5),
    patrol(),
    "danger",
  ],
  
        player.onCollide("danger", () => {
    go("lose")
  }
```



### Challenges

One of the challenges I have encountered is&#x20;

### Evidence

## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect                                                | What actually happens                                                                                    | Pass/Fail |
| ---- | ------------ | ------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- | --------- |
| 1    | The  bot     | The bot should move between two boundaries                   | The bot moves between the set boundaries                                                                 | pass      |
| 2    | The bot      | The bot should flip its body when it is changing directions  | The bot moves left and right but when it changes directions it does not move the way the body is facing  | fail      |

![](<../.gitbook/assets/image (8).png>)
