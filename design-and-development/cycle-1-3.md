# 2.2.1 Cycle 4

##

## Design

in this cycle, i aim to add a bot to my game. the function of this bot is to shoot at the player when they as well as guard gates to the next level. I aim to add different types of bots with different abilities. &#x20;

### Objectives



* [ ] add a bots&#x20;
* [ ] make the bot move



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |
|               |     |

### Pseudocode

```
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

## Development

### Outcome



### Challenges

one of the challenges i have encountered it&#x20;

## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect                                                  | What actually happens                                                                                     | Pass/Fail |
| ---- | ------------ | -------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | --------- |
| 1    | the  bot     | the bot should move between two bondariys                      | the bot moves between the set bandoaryies                                                                 | pass      |
| 2    | the bot      | the bot should filps its bodys when it is changing directions  | the bot moves left and right but when it changes directions it does not the way to body of the is facing  | fail      |

### Evidence



<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
