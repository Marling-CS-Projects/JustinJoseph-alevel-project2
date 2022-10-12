# Cycle 3 obstacles

##

## Design

### Objectives

The objective of this cycle is to add obstacles to the game, this is to provide the player with challenges that they have to over come to complete the level.&#x20;

* [x] obstacles ( pits, traps, and spikes )

### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name                            | Use                                                                                                                                            |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre><code>player.onCollide</code></pre> | this variable is used when the character comes in contact with any obstacles (such as spikes and traps) or anything that is tags as dangerous  |
|   danger                                 | this variable is used in a way that if the player comes in contact with this variable name it will lead the player to death                    |

### Pseudocode

```
```

## Development

### Outcome

The outcome of this cycle is that i have succesfully implemented the stopwatch as well as a coin system in which the players can collect the coins and the coins  will be added to the scoreboard&#x20;

### Challenges

one of the challenges that i faced during the implant of the stopwatch is correctly positioning the stopwatch meter on the screen so that the player can see the stopwatch easily. I overcame this by adjusting the size of the font that was used and adjusting the positions of it as well as  placing the stopwatch below another  instrument that was displayed to the player &#x20;

## Testing

i test if the spike worked by with a spike this resulted in the players death&#x20;

### Tests

| Test | Instructions     | What I expect                                                                                                                                                                                                     | What actually happens                                                                                                                                 | Pass/Fail |
| ---- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | added my spikes  | the spikes will function in a manner where when the user going in contact with  the spikes the player will take damage which will lead to death if the player comes in contact with it in more than one occasion  | the spikes are add successfully  however when the player comes in contact with the spikes the player does not take any damages to the players health  | Fail      |
| 2    | stop watch       | when the player starts the game the stopwatch will start and once the player has completed he game by finishing the level the stop watch will stop                                                                | the stopwatch worked as expected                                                                                                                      | Pass      |

### Evidence

```javascript

  "a": () => [
    sprite("acid"),
    area(),
    solid(),
    mp(),
    origin("bot"),
    "danger"
  ],
  
  "s": () => [
    sprite("spikes"),
    area(),
    solid(),
    origin("bot"),
    pos(0, 28),
    scale(1.5, 1.5),
    "danger"
  ],
```

```javascript

  player.onCollide("danger", () => {
    go("lose")
  })
```
