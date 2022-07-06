# 2.2.1 Cycle 1

##

## Design

### Objectives

For my first cycle, I aim to set up the code environment that will be used throughout the project with  HTML so that my game can be played on a browser. With my second objective, I aim to insert a shape or object and be able to move the object via a keyboard without issue. &#x20;

* [x] set the game development environment
* [x] be able to control the character via the keyboard&#x20;
* [x] &#x20;set up the platforms&#x20;

### Usability Features

the controls - to enable my game to be intuitive for the player , they will be provide with a minimal amount of controls to move characters around. with the intension of keeping it simple &#x20;

### Key Variables

| Variable Name           | Use                                                                                                                                                     |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| controls ( a, d, space) | this controls the movement of the character by moving left , right and jump                                                                             |
| player                  |  the use of this variable is to add the player to the game whilst providing the player with a body which the components of the game can interact with.  |
| speed                   | it provides that value which depend on how fast the character moves .                                                                                   |

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

After fixing issues with the movement of the character&#x20;

### Challenges

The challenges of this cycle was setting up a movement feature for the first character. In my first attempt my code failed ; I figured out that i had over complicated the code i  used and instead i changed to the code to be more simpler. After which the character was able to move left , right and up with out hindrances. &#x20;

## Testing

Evidence for testing

### Tests

| Test | Instructions           | What I expect                                                                                                                               | What actually happens                                                                                                                     | Pass/Fail |
| ---- | ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | movement               | when I press "a" the player moves left and when I press d the player move right                                                             | when i press the controls the player disappears of the screen .                                                                           | Fail      |
| 2    | movement (second  try) | when I press "a" the player moves left and when I press d the player move right .lastly when "space" is pressed the character  should jump  | when i press "a" the character moves left. when i press "d " the character move right. Finally when i press "space" the character  jumps. | Pass      |
| 3    | platform               | the player should be able to stand, move and jump on the platform without falling through it .                                              | the character was successful and was able to stand and move on the platform                                                               | pass      |

### Evidence



![](<../.gitbook/assets/image (8).png>)
