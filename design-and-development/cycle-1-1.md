# Cycle 2: Coin and Camera

##

## Design

### Objectives

In this cycle, I aim to create a coin system such that in the process of playing the game the user collects coin which is stored and displayed in the corner of the screen for that level likewise the overall coins collected through the levels will also be displayed on the home screen/menu. The second aim I have is to add a screen-scrolling camera feature that will follow the character through the levels. &#x20;

* [x] Add coin system&#x20;
* [x] Scrolling camera&#x20;

### Usability Features

&#x20; score board - the score board will be available on the game screen so that player can see how many coins they have collect as well has a way to movie them self to get more coins

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

To begin my cycles development to add to coin to the game i proceed to create a coin for my game however, looking for design example i came across a coin the was already stored as a asset in kaboom.js , i opted to use the coin provided with in kaboom as it simple and recoginzable by the player and kept in line with the theme was trying to create.

![](<../.gitbook/assets/image (4) (4).png>)

Once i found the coin that appropriate for my game i add the coins file address to the code of my game as well giving the tag "coin" for easy future reference, this enables me to save time.

```
// this is the coin image that is used in the game 
loadSprite("coin", "sprites/coin.png");
```

After the reference for the coin was created i proceeded to give the coin it's defining properties . I first assigned the coin the variable letter "c" this enabled me to add the coin to a map at any location my choosing. Then after I used the reference coin to add the function sprite("coin") this is to make sure that when the player is in the game they can see the image of coins . Like mentioned in previous cycles i use the functions area() to give the coins a hit box which enables the player to collect the coin for when the each other hit box collided and i used the function solid(),  to ensure that player does not go through the coin and instead would being able to collect the coin . The last the functions i used to add the coin to the game was pos(x,y) and scale(), the function pos(0) was use to position the the coin in relation how far should coins sit above the ground or platform and the scale() function was used to ensure the size of the coin was not too large or too small . These function being extremely useful after running the code to ensure that the coin added correctly, before these function was added the coin would  be over size in proportion to the game as well as that the coins was not positioned correctly by the game as it tended to be placed in the ground as supposed to above it ; to ensure that the coins were at correct value used in the pos() and scale() was reached,  i incremented the value of them  until the correct position and size was reached.&#x20;

```
// this is the code that gives the coins in the game its properties.
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

To complete the function before being displayed to the player  the collected coins has to  added up and stored. This was done with with the variable called score.value as you can see when a player comes in contact with a coin the value that is stored in the variable is increment by 1 . Once this is done a second variable called score.text is used. This is  what the player will soon come to see in the game . in which that the text "score" is added right next to it will be the last variable score.value. subsequently this mean that the player will the text  "score" and then on the right of the number of point / coins they have accumulated whilst playing the game this will be shown in text form .&#x20;

<pre><code><strong>// this code enables the player to collect the coin.
</strong><strong>// score.text will present the total collected coin on the game screen  
</strong><strong>  player.onCollide("coin", (c) => {
</strong>    destroy(c)
    score.value += 1
    score.text = "score:" + score.value
  })
</code></pre>

Lastly, is to display the score to the player. Since already i have created the score system for the coins it was a manner of adding the variable name ( score) to a out display function. I did this by giving this function a const name of score which is the same variable name used in the creation in the coin system . After which i used one of the two commands i created score.text = "score:" + score.value this is to tell the program (kaboom.) what to call upon in which essentially it is just running this line multiple times . Once the text appears on the player's screen it needs to be positioned , using the function pos(24,24) it allows me to move the text anywhere on the screen i chose to keep it in the corner of the screen this is to prevent the player from being distracted . when adding this coin function i had issue with the game registering the coin and adding it to the scoreboard later i discovered through research that i was required to set an initial value for the variable score.value , this was done this with code { value: 0 } , by having this line it meant that the game start the player will have 0 coin balance, it is once they start collecting the coin it will increment and display it. Finally the two functions that were used to complete the coin system were fixed () which is used to keep the text in place instead of following the player around and secondly is scale (0.50) this function controlled the size of the text whilst in game . The aim was to have it big enough that it was readable whilst not too big that it obstructed the game view.

```

 // this code postion the score board in the game 
  const score = add([
    text("score: 0"),
    pos(24, 24),
    { value: 0 },
    fixed(),
    scale(0.50)
  ])
```

#### Outcome of camera

The aims of the character movement was to  create a scrolling camera in which that the game will follow the movement of the input instead of the player, despite it working in most directions it quickly appears that it did not follow the player correctly . If the player went up or down from a platform it  resulted in the game continues but the camera was not following the player. This led to me researching a way in which I could get the camera to follow the player in all directions. I later discovered that the program I was using kaboom to code my game had a function called comPos() which would follow any object around by a camera, I decide the insert the name of the player as well as the current position of the player, player.pos. Subsequently the position of the player would be the most current due to the use of the function player.Onupdate(). This enables the game to find the coordinate location of the player at all times; when this was all put together the camera feature begin to function as expected this is also shown in the test.

```
 // this code follows the player around in the game 
   player.onUpdate(() => {
    camPos(player.pos);
  })
```

### Challenges

During this cycle, I face two different challenges. The first challenge I encountered was letting the player able to pick up the coin. I overcame this by making representing the coins as a non-fixed object which enabled the player to collect the coins. the second challenge I encountered was when the coin present in the game they were to large . i solved this by adding the function scale() this allowed that control the size of the coins thus make the coins in proportion to the levels.&#x20;

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

![](<../.gitbook/assets/image (21).png>)![](<../.gitbook/assets/image (11).png>)
