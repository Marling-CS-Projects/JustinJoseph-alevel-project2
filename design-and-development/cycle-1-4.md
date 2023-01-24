# Cycle 5: Enemy

##

## Design

In this cycle, I aim to add a bot to my game. The function of this bot is to shoot at the player when they are within line of sight as well as guard gates to the next level. I aim to add different types of bots with different abilities. &#x20;

### Objectives



* [x] Add enemy&#x20;
* [x] Make the enemy move



### Usability Features

&#x20; the enemy should be big enough for the player to see and be able to avoid&#x20;

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



<pre class="language-javascript"><code class="lang-javascript"><strong>// this is the functioned used by the emimes, that enables them to move left and right at a set speed 
</strong><strong>function patrol(speed =75 ,dis= 16 , dir = 1) {
</strong>
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
</code></pre>

With the new feature developed I proceeded to incorporate everything together in a variable function that can be called upon when needed. I used "e" as the function name, within that it contains the enemy sprite image that the player would see when player the game, after which I used the area() to give the enemy a hitbox - this became very useful as it is a way for the game to end itself when the player comes in contact with the enemy (this is done when both player and enemy hitboxes overlap), then after the scale function was used, this is because when the sprite enemy was tested in the game I found it to be too big for the game and its surroundings. By giving it a scale of 3.5 it was within the right proportions to the game. then the new function patrol() was added which allowed the enemy to move in the specified area by itself with a set boundary. Lastly, since the purpose of the enemy is to be an obstacle I used the danger tag and catergorised it as such. By using the categorisation it has made the coding process more efficient due to the fact anything that falls under the danger tag means that the game will end itself and the lose scene will appear if the player comes in contact with it.&#x20;

<pre class="language-javascript"><code class="lang-javascript">// this is the code used to configure the ememies in the game 
  "e": () => [
    sprite("enemy"),
    area(),
    origin("bot"),
    body(),
    scale(3.5),
    patrol(),
    "danger",
  ],
<strong> 
</strong>        player.onCollide("danger", () => {
    go("lose")
  }
</code></pre>



### Challenges

One of the challenges I encountered whilst implementing the enemy into my game was that the enemy would fall off the platform whilst in testing . I overcame these challenges in two ways . One way was to shorten the distant the enemy travels this had worked successfully whilst the second was done in a create way in which i created on pixel block that would be place exactly where i want the enemy to stop and turn around however one floor i found this method was that the player would be affected by the small block when trying to jump onto the platform the block would run the risk of stop the player trying to get one  therefore i discontinued the second idea.&#x20;

### Evidence

## Testing

Evidence for testing

### Tests

| Test | Instructions                    | What I expect                                                                                                                                                       | What actually happens                                                                                                                                                                                    | Pass/Fail |
| ---- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | run the code                    | the to appear where it is placed on the map as well has eleimate the player if the player comes in contect with the enemy                                           | the player gets eliminated by the enemy when contact is made as well a the enemy appear on the selected location.                                                                                        | pass      |
| 2    | movement run test               | after the basics of the enemy is established, i am now test if the enemy will move from in the designated area . such as a patrol of the area                       | the enemy moves around . However the enemy when placed on a platform the enemy falles if the platform                                                                                                    | fail      |
| 3    | movement run test ( second try) | after the basics of the enemy is established, i am now test if the enemy will move from in the designated area in a specific pattern . such as a patrol of the area | After seen the failiure of the fisrt test i went back to the code and altered the distant that the enemy can travel once that was done the enemy can movie around on the platform with out falling of it | pass      |

![](<../.gitbook/assets/image (8) (4).png>)
