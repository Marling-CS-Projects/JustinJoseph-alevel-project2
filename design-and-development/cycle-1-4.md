# Cycle 5 enemy

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



To start off my development cycle I first created an enemy that the player can see and interact with. This persuaded me to keep my draw for my enemy simple with the intension of keeping pegi 12  as I was very keen to integrate the enemy and make it functional&#x20;

![](<../.gitbook/assets/image (10).png>)



Once the drawing for the enemy was created I uploaded it onto kaboom.js and added the image file address to the game code and gave it a tag id of " enemy" . This is what is done throughout the development cycle to refer when coding the enemy.

```javascript
loadPedit("enemy", "sprites/enemy.pedit");
```

Once the enemy was added to the game it was need for the enemy have a purpose in the game.  The function called patrols allow the enemy to move around in a set area  currently i have set the movement of the enemy only to left and right direction as this want i need in my game. this has been achieved with the two lines of code if (col.isLeft() || col.isRight()) { dir = -dir  to allows the enemy to move autonomously. with the subsequent line having the reference to the speed component.



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

With the new feture developed i procced to incorporate everything together in a varible function that can be called upon when need . i used e as the funciton name with in that it contains the enemy spirte image that the pleyr would see when player the game , after whic i used the area() to give the enmey a hit box - this became very use as it is a way for the game to end it self when the player comes in contact with the enymy ( this is done whne both player and eneymer hitboxs overlap) , then after the scale function was used , this is because when the psite enmy was tested in the game i found it to be too big for the game and it suuroundings by hgive a scle of 3.5 it was proporshion to the game. then the new fucntion patrol() was add this alloed the enemy to move in the specified area by itslef with set boundary. Lastly since the the purpose of the enemy is to be a obstcles i used the danger tag and catgoized it as such.  By using the cagtoriation it has made the coding process more effeicient due to the fact any thing that falls under the danger tag means that the game will end itslef and the lose scene if the player comes in contact with it.&#x20;

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
| 2    | The bot      | The bot should filp its body when it is changing directions  | The bot moves left and right but when it changes directions it does not move the way the body is facing  | fail      |



<figure><img src="../.gitbook/assets/image (1) (3) (2).png" alt=""><figcaption></figcaption></figure>
