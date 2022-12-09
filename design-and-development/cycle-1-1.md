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

I have successfully added a coin scoreboard to my game as well as successfully being able to move the camera around with the player.

### Outcome

To begin my cycles development ot add to coin to the game i proceed to cretae a coin for my game however shilt liook for deisgn example i came acroos a coin the was already stored as a assect in kaboom.js , i opted to use the coin provied with in kaboom as it smple , regionsable by the player and kept in line with the theme was tryin to create.

![](../.gitbook/assets/image.png)

Once i found the coin that apporate for my game i add the coins file adress to the code of my game as well giving the tag "coin" for easy future refferent enablingme ot save time.

```
loadSprite("coin", "sprites/coin.png");
```

After the reference for the coin was created i proceeded to give the coin it's defining properties . I first assigned the coin the variable letter "c" this enabled me to add the coin to a map at any location my choosing. Then after I used the reference coin to add the function sprite("coin") this is to  make sure that when the player is in the game they see the image of coins . Like mentioned in previous cycles i use the functions area() to give the coins a hit box which enable the player to collect the coin for when the each other hit box collided and i used the function solid(),  to ensure that player does not go through the coin out would being able to collect it and it can be recognized by the game as component of the game. the last the functions i used to add the coin to the game was pos(x,y) and scale(), the function pos(0) was use to position the the coin in relation how far should coins sit above the ground or platform and the scale() function was used to ensure the size of the coin was not too large or too small . These function being extremely useful after running the code to ensure that the coin added correctly, before these function was added the coin would  be over size in proportion to the game as well as that the coins was not positioned correctly by the game as it tended to be placed in the ground as supposed to above it , to ensure the at correct value used in the pos() and scale() was reached,  i incremented the value of them  until the correct position and size was reached.&#x20;



```
  "c": () => [
    sprite("coin"),
    area(),
    solid(),
    origin("bot"),
    pos(0, 10),
    scale(0.75, 0.75),
    "coin"
  ],
```

To complete the coin function i the coins collects by the player in the game shoud be resented to the play during the game.&#x20;

```
  player.onCollide("coin", (c) => {
    destroy(c)
    score.value += 1
    score.text = "score:" + score.value
  })
```

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



<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>
