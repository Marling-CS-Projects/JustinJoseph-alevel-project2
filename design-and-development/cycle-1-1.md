# Cycle 2 coin and camera

##

## Design

### Objectives

In this cycle, I aim to create a coin system such that in the process of playing the game the user collects coin which is stored and displayed in the corner of the screen for that level likewise the overall coins collected through the levels will also be displayed on the home screen/menu. The second aim I have is to add a screen-scrolling camera feature that will follow the character through the levels. &#x20;

* [x] Add coin system&#x20;
* [x] Scrolling camera&#x20;

### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use                                                                                                                          |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Coin          | When the player comes in contact with a  coin the coin itself will disappear and the score will be added to the scoreboard.  |
| Campos        | The use of this variable is to enable the camera to move with the player wherever the player goes.                           |

### Pseudocode

Coin system

```

	player.onCollide("coin", (c) => {
		destroy(c)
    score.value += 1
    score.text = "score:" + score.value
  })

const score = add([
  text("score: 0"),
  pos(24,24),
  { value : 0},
  fixed(),
  scale(0.50)
])


```

```
player.onUpdate(() => {
  camPos(player.pos);  
})
```

## Development

### Outcome

I have successfully added a coin scoreboard to my game as well as successfully being able to move the camera around with the player.

### Challenges

During this cycle, I face three different challenges. The first challenge I encountered was letting the player able to pick up the coin. I overcame this by making representing the coins as a nonfixed object which enabled the player to collect the coins. the second challenge I encountered was displaying the added coins to the game while the game was being played.&#x20;

## Testing



### Tests

| Test | Instructions | What I expect                                                                                                                                          | What actually happens                                                                                                                                                                       | Pass/Fail |
| ---- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | The camera   | When I move the player left, right, up and down the camera should follow them in that direction.                                                       | The camera will follow the player when they move left and right. However when the player wants to jump up or go down the camera will not follow the player.                                 | Fail      |
| 2    | The camera   | When I move the player left, right, up and down the camera should follow them in that direction.                                                       | In my second try the camera will follow the player in any direction the player moves in the game.                                                                                           | Pass      |
| 3    | The coin     | When the coin is added it will hover  above the ground and be in scale with respect to the rest of the map.                                            | I added the coin to my game however it was scaled too big in respect to the background.                                                                                                     | Fail      |
| 4    | The coin     | When the coin is added it will hover above the ground and be in scale with respect to the rest of the map.                                             | When I rewrote the code I added a scale factor to alter the size of the coin and now the coin is the perfect size ratio to the background as well that the coin hovers above the platform.  | Pass      |
| 5    | The coin     | When the player goes in contact with coins the coin should disappear and be added to the scoreboard which the player can see whilst playing the game.  | When the player comes in contact with the coins, the coins are collected and added to the scoreboard.                                                                                       | Pass      |

### Evidence



```javascript
// coin 
   
  "c": () => [
    sprite("coin"),
    area(),
    solid(),
    origin("bot"),
    pos(0,10),
    scale(0.75,0.75),
    "coin"
  ],
               
   player.onCollide("coin", (c) => {
      destroy(c)
    score.value += 1
    score.text = "score:" + score.value
  })

const score = add([
  text("score: 0"),
  pos(24,24),
  { value : 0},
  fixed(),
  scale(0.50)
])

```

```javascript
 // player camera code 
 
player.onUpdate(() => {
  camPos(player.pos);  
})
```

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>
