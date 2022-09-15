# 2.2.1 Cycle 2

##

## Design

### Objectives

In this cycle, I aim to create a coin system such that in the process of playing the game the user collects coin which is stored and displayed in the corner of the screen for that level likewise the overall coins collected through the levels will also be displayed on the home screen/menu. The second aim I have is to add a screen scrolling camera feature that will follow the character through the levels. &#x20;

* [x] add coin system&#x20;
* [x] scrolling camera&#x20;

### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use                                                                                                                          |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| coin          | when the player comes in contact with a  coin the coin itself will disappear and the score  will be added to the scoreboard  |
|  pos          |                                                                                                                              |

### Pseudocode

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

## Development

### Outcome

### Challenges

Description of challenges

## Testing

E

### Tests

| Test | Instructions | What I expect                                                                                                                                         | What actually happens                                                                                                                                                                   | Pass/Fail |
| ---- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | the camera   | when i move the pleyer left , right , up and down the camera should follow them in that direction                                                     | the camera will follow the player when they move left and right . however when the player wants to jumps up or go down the camera wil not follow the player                             | Fail      |
| 2    | the camera   | when i move the pleyer left , right , up and down the camera should follow them in that direction                                                     | in my second try the camera will follow the player in any direction the player moves in the game                                                                                        | pass      |
| 3    | the coin     | when the coin is added it will hover  above the ground and be in scale in respect to the of the map                                                   | i added the coin to my game however it was scaled too big in respect to the background                                                                                                  | fail      |
| 4    | the coin     | when the coin is added it will hover  above the ground and be in scale in respect to the of the map                                                   | when i rewritten the code i added a  scale factor to the size of the coin and now the coin is the perfect size ratio to the background aswell that  the coin hovers above the platform  | pass      |
| 5    | the coin     | when the player goes in contact with coins the coin should dissaplear and be add to the score board which the player can see whilst playing the game  | whent he player came in contact with the coins the coin are collected and added to the scroe board                                                                                      | pass      |

### Evidence



<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>this images shows that the coin are place in the corrwect place and in the right postions </p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p><mark style="background-color:blue;"><strong>this images show that the player can collect the coins and it will be added to the score board on the top left</strong></mark> </p></figcaption></figure>
