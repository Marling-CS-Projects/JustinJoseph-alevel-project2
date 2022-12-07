# Cycle 3 obstacles

##

## Design

### Objectives

The objective of this cycle is to add obstacles to the game, this is to provide the player with challenges that they have to overcome to complete the level.&#x20;

* [x] create the sprite image for the obstacles  ( the spikes , pits and traps )
* [x] add the obstacle to the game and place the obstacles places in the map
* [x] add a functionally of death when the player coming contact with the obstacles&#x20;

### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name                             | Use                                                                                                                                               |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| <pre><code>player.onCollide
</code></pre> | This variable is used when the character comes in contact with any obstacles (such as spikes and traps) or anything that is tagged as dangerous.  |
|   danger                                  | This variable is used in a way that if the player comes in contact with this variable name it will lead the player to death.                      |

### Pseudocode

```

  spikes : () => [
    sprite("spikes"),
    give area for a hitbox
    origin("bot"),
    location of the spkies 
    size of the spikes 
    "danger"
  ],
  
  playerCollides(danger)
    show death scene
  })
  
```

## Development

### Outcome

&#x20;Adding a functional obstcle was the main object, to ensure that i save time i proceed to draw a simple design of the  spikes, i look at other exampkes i want to make sure that the spikes were recominable .

![](<../.gitbook/assets/image (9).png>)

![](<../.gitbook/assets/image (12).png>)



```
loadPedit("spikes", "sprites/spikes.pedit");
loadPedit("spikesdown", "sprites/spikesdown.pedit");
```

```javascript

 
  
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

### Challenges

One of the challenges that I faced during the implant of the stopwatch is correctly positioning the stopwatch meter on the screen so that the player can see the stopwatch easily. I overcame this by adjusting the size of the font that was used and adjusting the positions of it as well as  placing the stopwatch below another  instrument that was displayed to the player &#x20;

The outcome of this cycle is that I have successfully implemented the stopwatch as well as a coin system in which the players can collect the coins and the coins  will be added to the scoreboard&#x20;

## Testing

I test if the spike worked by with a spike this resulted in the player's death&#x20;

### Tests

| Test | Instructions      | What I expect                                                                                                                                                                                                    | What actually happens                                                                                                                                   | Pass/Fail |
| ---- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Added the spikes  | The spikes will function in a manner where when the user comes in contact with the spikes the player will take damage which will lead to death if the player comes in contact with it in more than one occasion. | The spikes were added successfully however when the player comes in contact with the spikes the player does not take any damage to the players health.  | Fail      |
| 2    | Stopwatch         | When the player starts the game the stopwatch will start and once the player has completed he game by finishing the level the stopwatch will stop.                                                               | The stopwatch worked as expected.                                                                                                                       | Pass      |

### Evidence
