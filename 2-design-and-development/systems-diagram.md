# Design Frame

## Systems Diagram

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

This diagram shows the different parts of the game that I will focus on creating. I have split each section into smaller sub-sections. Throughout the development stage, I will pick one or two of these sections to focus on at a time to gradually build up and piece together the game. I have broken the project down this way as it roughly corresponds to the success criteria.

## Usability Features

Usability is an important aspect of my game as I want it to be accessible to all. There are 5 key points of usability to create the best user experience that I will be focusing on when developing my project. These are:

### Effectiveness

Users can achieve the goal with completeness and accuracy. To do this, I will make it easy for the players to realise that they need to reach a goal in order to complete a level. I will make this goal clear to see so there is no confusion over where the players need to go.

#### Aims

* The player should be able to reach the end of the level without issues&#x20;
* Create a clear goal for any multiplayer modes

### Efficiency

The speed and accuracy with which a user can complete the goal. To do this, I will create a menu system that is easy to navigate through in order to find what you are looking for. The information which is more important can be found with fewer clicks.

#### Aims

* Create a menu system that is quick and easy to navigate through
* Create a controls system that isn't too complicated but allows the player to do multiple actions

### Engaging

The solution is engaging for the user to use. To do this, I will create 5 levels and an online multiplayer mode to keep the players engaged and allow them to have fun while playing the game. Using vector-style art will also make the game nicer to look at than blocks, so will draw more people in, keeping them engaged.

#### Aims

* Create a series of levels to work through
* Create a multiplayer mode to play
* Incorporate a style of game art that suits the game

### Error Tolerant

The solution should have as few errors as possible and if one does occur, it should be able to correct itself. To do this, I will write my code to manage as many different game scenarios as possible so that it will not crash when someone is playing it.

#### Aims

* The game doesn't crash
* The game does not contain any bugs that damage the user experience

### Easy To Learn

The solution should be easy to use and not be over complicated. To do this, I will create simple controls for the game. I will make sure that no more controls are added than are needed in order to keep them as simple as possible for the players.

#### Aims

* Create a list of controls for the game
* Create an in-level guide that helps players learn how to play the game

## Pseudocode for the Game

### Pseudocode for game

This is the basic code of the object to store the details of the game. With the use of these components it would allow me to draw my initial sketch of the my first level and enable to add the character in

```
import kaboom

background colour = "blue"
set window size to (500,700)

load in Character.pedit as "Character"
load in ground.pedit as "ground"
load in platform.pedit as "platform"
load in Spikes.pedit as "Spikes"

levelconfig = {
    set width to 32
    set height to 32

    "=" set to sprite("Floor"){
        area(),
        origin("bottom")
    }
    
    "s" set to sprite("Spike "){
        area(),
        origin("bottom")
    }

    "p" set to sprite("platform"){
        area(),
        origin("bottom")
    }
}
```

### Pseudocode for a level

This shows the basic layout of code for a kacoom level and game scene.&#x20;

```
const map = [

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
