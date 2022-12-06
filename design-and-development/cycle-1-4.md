# Cycle 5 enemy

##

## Design

In this cycle, I aim to add a bot to my game. The function of this bot is to shoot at the player when they are within line of sight as well as guard gates to the next level. I aim to add different types of bots with different abilities. &#x20;

### Objectives



* [x] Add a bots&#x20;
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



### Challenges

One of the challenges I have encountered is&#x20;

## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect                                                | What actually happens                                                                                    | Pass/Fail |
| ---- | ------------ | ------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- | --------- |
| 1    | The  bot     | The bot should move between two boundaries                   | The bot moves between the set boundaries                                                                 | pass      |
| 2    | The bot      | The bot should filp its body when it is changing directions  | The bot moves left and right but when it changes directions it does not move the way the body is facing  | fail      |

### Evidence

```javascript
function patrol(speed = 60, dir = 1) {

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



<figure><img src="../.gitbook/assets/image (1) (3) (2).png" alt=""><figcaption></figcaption></figure>
