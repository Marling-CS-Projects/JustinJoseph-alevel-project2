# Cycle 1: Setup

##

## Design

### Objectives

For my first cycle, I aim to set up the basics of my project before adding additional features. For this, the first object would be to create a coding environment such as kaboom.js along with a GitHub repository to back up my work. This is followed by creating a simple platform level that would be used for all of my tests of the components I would be using (this initial level would evolve into an actual level which would be a proper game level). Lastly, is to add a character with the ability to move via the use of a keyboard as the input. The use of the keyboard is more beneficial for the environment the user will interact the game with (the browser) compared to touch on a smartphone. &#x20;

* [x] Set the game development environment
* [x] Be able to control the character via the keyboard&#x20;
* [x] Set up the platforms&#x20;

### Usability Features

Controls - the controls for the player will be done in a simple manner by have A for left ,D for right and the space bar for jump / double jump&#x20;

### Key Variables

| Variable Name          | Use                                                                                                                                                  |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Controls (a, d, space) | This controls the movement of the character by moving left, right, and to jump                                                                       |
| Player                 | The use of this variable is to add the player to the game whilst providing the player with a body which the components of the game can interact with |
| move\_speed            | It provides a value which determines how fast a player moves                                                                                         |

### Pseudocode

```
import kaboom from "kaboom"

// initialize context
kaboom()


// These are the images assets of the game. this is what the player will see  when playing the game 
 // the is the ground images 
loadPedit("ground", "sprites/ground.pedit");
 // this is the image of the player 
loadPedit("goro", "sprites/goro.pedit");
 // this is the images of the background of the game 
loadSprite("background", "sprites/background.png");



//this is the map for the level that the player will play in 
const map = [
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '                       ',
  '  =====================',
]
// componets of the game 
const levelcfg = {
  width:32,
  height:32,
  
  "=": () => [
	sprite("ground"),
	area(),
	solid(),
	origin("bot"),
	],
 
}

addLevel(map,levelcfg)

// adding the player to the game and it`s characteristic

const player = add([
  sprite('goro'),
  pos(30,0),
  body(),
  area(),
])

// players movement in the game 

const move_speed = 500

keyDown('left',()=> {
 player.move(-move_speed,0) 
})

keyDown('right',()=> {
 player.move(move_speed,0) 
})

const Jump_force = 500

keyPress('space', () => {
 if(player.grounded())
 player.jump(Jump_force)
})
```

## Development

### Outcome



To commence my project i first set the dimension of my game, which meant that my game is to be  presented to the player in a viewing frame of 1000 pixel width by 700 pixel height. I found this was an appropriate frame size as it did not show much to the player thus enabling me to keep in line to my aspirations in 1.4a. Once I found the right game frame I proceeded to give my game a background colour to ensure my game was appealing.

```javascript
kaboom({
// the viarble background is to set the colour of the backgorund this is done in the number and uses the RGB color number
  background: [135, 206, 235],
// the viarbles width and height to get the stage where the player can play in. to increase the size of the game in the x axes increase the width number value 
  width: 1000,
// to incrase the game play size in the y direction increase the height value 
  height: 700,

```

After the game's dimensions and the background colour were created, I proceeded to develop the essential assets ( also known as sprites) I would be using these in the game; these mainly include the character and platform ground blocks for now. The designs of the asset were done in retro as well as cartoon styles, so the game does not become graphically inappropriate, thus being able to stay in the claimed age range of pegi 12.

```javascript

// these are the images used in the game that the player will see 
loadPedit("ground", "sprites/ground.pedit");
// this is the images for the character 
loadPedit("goro", "sprites/goro.pedit");
// image fro the game background
loadSprite("background", "sprites/background.png");
// image for the platform that the player will stand on
loadPedit("platform", "sprites/platform.pedit");
```

Once I had completed creating the essential assets I needed for the game for the early stage, I turned my attention to designing the level. For my convenience and to increase productivity/ efficiency, the program in use to code my game (kaboom) allows programmers to assign a variable name to the assets. This enabled me to assign variables for the game. For example, in the ground, the "=" symbol, the platform was given "p" the spikes were given "s”. However, I decided not to provide the main character with a variable name because adding the player as a separate asset to the game will make it easier to manipulate the player. When designing for the level, I created the level in a way that it was large enough that the player got time to explore the game and overcome the obstacles so that the player does not complete the level too quickly but not overly large that the player will be frustrated with the game.

```javascript
// this is the level map for the game in which the player will play in 
const map = [
  '                                                                              ',
  '         ppp              ppp                pp                         ppppp',
  '                                                                             ',
  '                                                                            ',
  '                                                          pppp                   ',
  ' ppp            ppppp                      ppp                               ',
  '                                                                             ',
  '                                                                             ',
  '                                                                            ',
  '      pppp          ppppp           ppppp                  ppppppppppppp   ',
  '                                                                             ',
  '                                                                             ',
  '                                                   pppp                          ',
  '                                                                             ',
  '                                                          pppp                   ',
  ' pppp                                                                        ',
  '                                                                             ',
  '                                                                             ',
  '                                                                              ',
  '             ppppp             ppppp                ppppp              pppp ',
  '                                                                             ',
  '                                                                              ',
  '                                                                             ',
  '   pppp               pppppp             pppppp              pppppp         ',
  '                                                                              ',
  '                                                                             ',
  '                                                                             ',
  '             pppppp                            ppppppp          pppp      ',
  '                                                                             ',
  '                                                                             ',
  '                                                                             ',
  '                                                                         ',
  '============================================================================',
]

// this is the configuration setting for the size for the level 
const levelcfg = {
  width: 32,
  height: 40,

```

As mentioned above, the program I am using to create my game enables me to add components to the game simply. This has been displayed below in which that kaboom allows me to add the components I want into the game, such as the ground, block and platforms. After which, I can add the relevant information to give the game's components their roles. An example of this would be the ground. I have given assigned it the variable "=" as well as making the ground a solid object which allows the player to stand and move around on it, after which I gave it an area in which it can operate in, this is to prevent the component from interfering with other aspects of the game. This method enabled me to streamline the coding process for adding components which in turn saves time that I could use to add functions to the game.

\


```javascript
// these are levels componets of the game that the player will see 
// the "=" presents the ground
  "=": () => [
    sprite("ground"),
    area(),
    solid(),
    origin("bot"),
  ],


// this is the backgorund colour / images the will be used in the game 
  "b": () => [
    sprite("background"),
    area(),
    scale(2),
    width(32),
    height(15),
    pos(24, -240),
  ],

// this is the code for the platform in the game showing its area and it is a solid object that plats can stand on
  "p": () => [
    sprite("platform"),
    area(),
    solid(),
    origin("bot"),
  ],
//this is a platform of a different size
  "j": () => [
    sprite("platform3"),
    area(),
    solid(),
    mp(),
    origin("bot"),

  ],
```

Once the relevant component was added to the game for the early stage development, I proceed to turn my attention to adding the character to the game. This was done in three stages, with the first stage being designing the character, to save time and to ensure that the game met the pegi 12 criteria I designed the character in a retro and cartoonish style as shown in the image below.



<figure><img src="../.gitbook/assets/image (3) (4).png" alt=""><figcaption></figcaption></figure>

Once the first stage was completed, I added the image file address ( with the assets file being stored in the game) to the game. Additionally, I provided the file with a tag name "goro" this is to make it simpler for me to refer to the file tough out development phase.

```
// this is the code that will loade the players images into the game for the playerto see 
loadPedit("goro", "sprites/goro.pedit");
```



The final stage was to add the character into the game itself. This was done by giving the character two main functions which enable the character to be noticed by the game, one function was the body() function. This function allows the player to interact with other components of the game ( such as the ground platform, spikes and etc ) by being able to interact with other components, the player can take damage and collect assets that can be added to the scoreboard. The second main function was the area() function that enabled the character to have a designated hitbox area, this means that there will be a designated boundary in which the game components can take action on the player if the boundary overlapped with the components of the game. The last addition to the character that enabled it to be fully functional was the pos(149, 1216), and scale (2) variables. By adding the variable the pos(149, 1216), it enables to set off the potion of the character to use (x,y) coordinates on where the character starts in the level and subsequent levels. Furthermore, the scale() variable enables me to set a size to the character by scaling up or down, by doing so it allows me to make the character proportional to the game and not be oversize which will hinder the user gaming experience.

```javascript
 // this is the code that give the player its ability, as well as it apperance  , the size and it`s starting postion in the gmae 
   const player = add([
    sprite('goro'),
// this provides character with the position on where it starts inthe game .
// the first value "149" refers to the x direction in the game 
    pos(149, 1216),
    body(),
    area(),
    scale(2),
  ])
```

My final objective of this cycle was to give the player the ability to move in all directions as well as give the character the ability to jump. I started to code this function with a move\_speed this is the name of the function i would be using to refer to the speed of the character during the creation of this function. I set the speed of the character to 250. However, I later discovered during testing this was too slow a movement of the character, which later on, I changed the move\_speed to 500 this proved sufficient speed for the move of the character. Once the speed of the character was determined, i also decided to add a jumping force to my game which enable me to give my character the right amount of force that allow the player to jump off a solid object ( like at a platform or the ground). I put this jumping force under the variable name called Jump\_force, which I set to 10. Lastly, was add the control using the function called KeyDown, with this function i was able to give each control a corresponding letter on the keyboard, for example, i decide to go with "a" for left,"d" for right and space for jump . To control the direction that the player going in i used the command called player.move() in the x,y components. since i have already set that Move\_ speed works only in the x direction by adding a minus at the front of the const variable move\_speed it makes the player go to the left whilst keeping the const variable as it is, it would make it go to the right.

```javascript
// the varible " move_speed" give the player it`s speed in the game 
  const move_speed = 500
  
//  this function gives the player the abilty to move left 
  keyDown('a', () => {
    player.move(-move_speed, 0)
    player.flipX(true)
  })

// this function  gives the player the abilty to  move right 
  keyDown('d', () => {
    player.move(move_speed, 0)
    player.flipX(false)
  })
// this is the forces the player will jump with up and down 
  const Jump_force = 10
// this is the code for double jump
  keyPress('space', () => {
    player.doubleJump()
  })

```

### Challenges

The challenge of this cycle was setting up a movement feature for the first character. In my first attempt, my code failed; I figured out that I had over-complicated the code I used and instead I changed the code to be simpler. After which the character was able to move left, right, and up without hindrances. l also found it a challenge to find the correct speed for the player i resolved this by going up in 100s until i found a satisfactory speed value&#x20;

## Testing

| Test | Instructions           | What I expect                                                                                                                                   | What actually happens                                                                                                                       | Pass/Fail |
| ---- | ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Movement               | When I press "A" the player moves left and when I press "D" the player move right.                                                              | When I use the controls the player disappears from the screen.                                                                              | Fail      |
| 2    | Movement (second  try) | when I press "A" the player moves left and when I press "D" the player move right. Also when "Space bar" is pressed the character  should jump. | When I press "A" the character moves left. when i press "D" the character move right. Finally when i press "Space bar" the character jumps. | Pass      |
| 3    | Platform               | The player should be able to stand, move and jump on the platform without falling through it.                                                   | The character was able to stand and move on the platform                                                                                    | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
