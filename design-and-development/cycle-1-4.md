# Cycle 5 enemy

##

## Design

in this cycle, i aim to add a bot to my game. the function of this bot is to shoot at the player when they as well as guard gates to the next level. I aim to add different types of bots with different abilities. &#x20;

### Objectives



* [x] add a bots&#x20;
* [x] make the bot move



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name                   | Use                                                                                                                                                                                           |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre><code> patrol</code></pre> | this variable is used to store the actions ( the command ) of the enemy bot which is the movement of the enemy from left to right and what will happen is the player coilies with the player  |
| this .move                      | this is the variable used to give the bot the speed and direction to going in left and right                                                                                                  |
|                                 |                                                                                                                                                                                               |

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
}</code></pre>

## Development

### Outcome



### Challenges

one of the challenges i have encountered it&#x20;

## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect                                                  | What actually happens                                                                                     | Pass/Fail |
| ---- | ------------ | -------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------- |
| 1    | the  bot     | the bot should move between two boundaries                     | the bot moves between the set boundaries                                                                  | pass      |
| 2    | the bot      | the bot should filps its bodys when it is changing directions  | the bot moves left and right but when it changes directions it does not the way to body of the is facing  | fail      |

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



<figure><img src="../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>
