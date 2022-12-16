# Cycle 3: Obstacles

##

## Design

### Objectives

The objective of this cycle is to add obstacles to the game, this is to provide the player with challenges that they have to overcome to complete the level.&#x20;

* [x] Create the sprite image for the obstacles (the spikes, pits and traps)
* [x] Add the obstacle to the game and place the obstacles places in the map
* [x] Add a functionally of death when the player coming contact with the obstacles&#x20;

### Usability Features

&#x20; the obstacles will be bright and clear so that the players can avoid them

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

The first tasks in order to complete this cycles was to draw a set of obstacles that the player can identify as dangerous object thus encouraging them to stay clear this lead me to draw the design for a spikes. With the use of the simple design it enabled me to save time and move on to adding the obstacle into the game.

![](<../.gitbook/assets/image (9) (3).png>)

![](<../.gitbook/assets/image (12).png>)

&#x20;Once the design of the obstacle was create i upload the obstcle in the kaboom.js and give the each obstcles a tag  which i use to reffer back through out the development process .

```
loadPedit("spikes", "sprites/spikes.pedit");
loadPedit("spikesdown", "sprites/spikesdown.pedit");
```

From using my knowledge that l have gained from cycle 1 and 2 i decide to alter only certain aspects of the code that will give the obstacles its role this has enabled me to save a vast amount of time. The alteration i made was to the position of the obstacles to ensure that the obstacle sat in the correct place as well as creating a new category called "danger" this is for obstacles and any component of the game that can instant lead to the player staring the game again i would use this category as a reference though the development process.

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

The last function that was needed to complete this cycle is when the player comes in contact with the obstacles which results in game over for the player. For this to be achieved l started off with use of the function .oncollide ("danger") this meant that any player who comes in contact with a object in game categorized as danger (an example of this would be mentioned above with spikes) would referred to the go("lose") this will end the game subsequently displaying the game over scene giving the player the option the start the game again.

```javascript

  player.onCollide("danger", () => {
    go("lose")
  })
```

### Challenges

The first challenge I faced when adding the obstacle was that the player did not die when they come in contact with the obstacles . i overcame this by tagging the obstacles as " danger " this meant that any  player that comes in contact with a obstacles the game will end

## Testing

I test if the spike worked by with a spike this resulted in the player's death&#x20;

### Tests

| Test | Instructions                      | What I expect                                                                                                               | What actually happens                                                                                               | Pass/Fail |
| ---- | --------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Added the spikes                  | The spikes will function in a manner where when the user comes in contact with the spikes the player should fail the level  | The spikes were added successfully however when the player comes in contact with the spikes the player does not die | Fail      |
| 2    | Added the spikes (second attempt) | The spikes will function in a manner where when the user comes in contact with the spikes the player should fails the level | After the some alteration to the code when the player comes in contact with the spikes the player fails the level   | pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (14) (2).png" alt=""><figcaption></figcaption></figure>
