# Cycle 1 set up

##

## Design

### Objectives

For my first cycle, I aim to set up the basics of my project before adding additional features. For this, the first object would be to create a coding environment such as visual studio code along with a GitHhub repository to back up my work. This is followed by creating a simple platform level that would be used for all of my tests of the components I would be using (this initial level would evolve into an actual level which would be a proper game level). Lastly, is to add a character with the ability to move via the use of a keyboard as the input. The use of the keyboard is more beneficial for the environment the user will interact the game with (the browser) compared to touch on a smartphone. &#x20;

* [x] Set the game development environment
* [x] Be able to control the character via the keyboard&#x20;
* [x] Set up the platforms&#x20;

### Usability Features

Movement - to enable my game to be intuitive for the player, they will be provided with a minimal amount of controls to move characters around. with the intention of keeping it simple &#x20;

### Key Variables

| Variable Name          | Use                                                                                                                                                  |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Controls (a, d, space) | This controls the movement of the character by moving left, right, and to jump                                                                       |
| Player                 | The use of this variable is to add the player to the game whilst providing the player with a body which the components of the game can interact with |
| Speed                  | It provides a value which determines how fast a player moves                                                                                         |

### Pseudocode

```
import kaboom from "kaboom"

// initialize context
kaboom()


// load assets
loadPedit("ground", "sprites/ground.pedit");
loadPedit("goro", "sprites/goro.pedit");
loadSprite("background", "sprites/background.png");

// background 
  add([
    sprite("background", {width: width(), height: height()})
  ]);

//level
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
// adding player 

const player = add([
  sprite('goro'),
  pos(30,0),
  body(),
  area(),
])

//movement 

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



To commence my project i first set the dimension of my game which meant that my game present to the player in a viewing frame of 1000 pixel width by 700 pixel height i found this was an appropriate frame size as it did not show much to the player thus enabling me to keep in line to my aspirations in 1.4a. Once I found the right game frame I proceeded to give my game a background colour to ensure my game was appealing.

```javascript
kaboom({
  background: [135, 206, 235],
  width: 1000,
  height: 700,
})
```

After the game's dimensions and the background colour were created, I proceeded to create the essential assets ( also known as sprites) I would be using in the game; these mainly include the character , platform , the spikes and ground blocks for now. the designs of the asset was done in a retro as well as cartoons styles so the game does not become graphically inappropriate thus being able to stay in the claimed age range of pegi 12.

```javascript

// load assets
loadPedit("ground", "sprites/ground.pedit");
loadPedit("goro", "sprites/goro.pedit");
loadSprite("background", "sprites/background.png");
loadPedit("spikes", "sprites/spikes.pedit");
loadPedit("platform", "sprites/platform.pedit");
loadPedit("spikesdown", "sprites/spikesdown.pedit");
loadPedit("block", "sprites/block.pedit");
loadPedit("platform1", "sprites/platform1.pedit");
loadPedit("goro2", "sprites/goro2.pedit");
loadPedit("platform3", "sprites/platform3.pedit
```

Once I had completed creating the essential assets I need for the game for the early stage, I turned my attention to designing the level. For my convenience and to increase the productive/ efficiency the program in use to code my game (kaboom) allow programmers to assign variable name to the assets, this enabled me to assign variables for the game the game. For example, in the ground the "=" symbol, the platform was given "p" the spikes were given "s”. However, I decided not to give the main character a variable name this was because by adding the player as a separate asset to the game it will make it easier to manipulate the player.



```javascript
const map = [
  '                                                                         @      ',
  '         ppp              ppp                pp                         ppppp',
  '                                                                             ',
  '                                                           ccc                 ',
  '                                                          pppp                   ',
  ' ppp            ppppp        j              ppp                               ',
  '                                                                             ',
  '                                                                             ',
  '                     sccs             cscs                         ccssc           ',
  '      pppp          ppppp           ppppp          a        ppppppppppppp   ',
  '                                                                             ',
  '                                                                             ',
  '                                                   pppp                          ',
  '                                                                             ',
  '                                                          pppp                   ',
  ' pppp                                                                        ',
  '                                                                             ',
  '                                                                             ',
  '                cc               ss                  sss                ccc     ',
  '             ppppp             ppppp                ppppp              pppp ',
  '                                                                             ',
  '                                                                              ',
  '                       cs                   ss                                   ',
  '   pppp               pppppp             pppppp              pppppp         ',
  '                                                                              ',
  '                                                                             ',
  '                                                                             ',
  '             pppppp           m                 ppppppp          pppp      ',
  '                                                                             ',
  '                                                                             ',
  '                                                                             ',
  '               s            e    s                             e          s   ',
  '============================================================================',
]


const levelcfg = {
  width: 32,
  height: 40,

```

```javascript

  "=": () => [
    sprite("ground"),
    area(),
    solid(),
    origin("bot"),
  ],


  "l": () => [
    sprite("block"),
    area(),
    solid(),
    origin("bot"),
  ],

  "b": () => [
    sprite("background"),
    area(),
    scale(2),
    width(32),
    height(15),
    pos(24, -240),
  ],

  "p": () => [
    sprite("platform1"),
    area(),
    solid(),
    origin("bot"),
  ],

  "m": () => [
    sprite("platform"),
    area(),
    solid(),
    mp(),
    origin("bot"),
  ],


  "j": () => [
    sprite("platform3"),
    area(),
    solid(),
    mp(),
    origin("bot"),

  ],
```

```javascript
  const player = add([
    sprite('goro'),
    pos(149, 1216),
    body(),
    area(),
    scale(2),
  ])
```

```javascript

  const move_speed = 500
  const BULLET_SPEED = 1200

  keyDown('a', () => {
    player.move(-move_speed, 0)
    player.flipX(true)
  })


  keyDown('d', () => {
    player.move(move_speed, 0)
    player.flipX(false)
  })

  const Jump_force = 10

  keyPress('space', () => {
    player.doubleJump()
  })

```

### Challenges

The challenge of this cycle was setting up a movement feature for the first character. In my first attempt, my code failed; I figured out that I had over-complicated the code I used and instead I changed the code to be simpler. After which the character was able to move left, right, and up without hindrances. &#x20;

## Testing

| Test | Instructions           | What I expect                                                                                                                                   | What actually happens                                                                                                                       | Pass/Fail |
| ---- | ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Movement               | When I press "A" the player moves left and when I press "D" the player move right.                                                              | When I use the controls the player disappears from the screen.                                                                              | Fail      |
| 2    | Movement (second  try) | when I press "A" the player moves left and when I press "D" the player move right. Also when "Space bar" is pressed the character  should jump. | When I press "A" the character moves left. when i press "D" the character move right. Finally when i press "Space bar" the character jumps. | Pass      |
| 3    | Platform               | The player should be able to stand, move and jump on the platform without falling through it.                                                   | The character was able to stand and move on the platform                                                                                    | Pass      |

### Evidence



![](<../.gitbook/assets/image (8) (1).png>)
