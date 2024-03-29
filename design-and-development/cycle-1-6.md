# Cycle 7: Exit Door

##

## Design

### Objectives

The objective of this level is to add an exit door for the player. Once the player has passed through the door the level is completed and if the player chooses to they can be taken to the level after which going through that door the level is fully completed.

* [x] Add an exit door
* [x] Takes the player to the next level  &#x20;
* [x] Once the player has completed all of the levels the win scene will appear   &#x20;





### Usability Features

&#x20; clear exit- the portal to the exit level should be easy to find by the player this can be done by make the portal big

### Key Variables

| Variable Name | Use                                                                                                                                                                                         |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Win scene     | The variable is used to show the player the win scene if the player has reached the exit of the level                                                                                       |
|  Add          | This is to include objects, text, and components of the game. In this case, it is to add text and  position it on the screen for when the player wins the level (by getting to the portal)  |

### Pseudocode

<pre><code><strong>if player collide with exit (
</strong><strong> go to next level
</strong><strong> )
</strong></code></pre>

```
    scene("you have win", > {
      add([
        text("win ", ),
        pos(x,y),
        origin("center"),
        color(white),
      ]);


      add([
        text("press enter to go back to the start menu ", ),
        pos((500, 350)),
        origin("center"),
        color(255, 255, 255),
        text
      ]);

      when pressed("enter", () => {
        go("start");
      })
    });
```

## Development

### Outcome

The first stage of completing this objective was to create a exit door and then add the exit  to the game in the from of a sprite as shown below .

<figure><img src="../.gitbook/assets/image (25) (1).png" alt=""><figcaption></figcaption></figure>

Once it was added to the game i also imported its file address and provided the portal with a tag

```
// this is the image for the exit/ portol in the game 
loadSprite("portal", "sprites/portal.png");
```

For the exit to be useful it has to be add to the level map. The portal uses the same properties as other component of the game but with the only mention able difference being that it has been categories with "exit" this will be come useful later during the development phase for the exit.&#x20;

```javascript
 // this is the code configuration for the exit / portal in the game 
  "@": () => [
    sprite("portal"),
    area(),
    solid(),
    origin("bot"),
// the portal has been tag with exit this enables the fucntion of when player commes in contract with exit
    "exit"
  ],
```

Once the exit was added to the game I wrote a code stating that when the player comes in contact with the exit the game should go to the win scene this is to the indicate to the player that they have completed the level and that player has the option to leave or continue in the game.

```javascript
 // this is the code for when the player has reached the final level and comes in contact with the portal 
   player.onCollide("exit", () => {
    go("win")
  })
```

For the final objective of this cycle was to provide the game with a win scene as well as a return to start screen. This is evident in the code below when the player has completed the level the player will be greeted by a win scene. whilst coding for this scene the i had to adjust the position of the " you have win" text which i achieved by using the command "pos(vec2(400, 200))," to move/ adjust the position of the text in the X and Y direction.&#x20;

```javascript
  // these are the different scene that are present in the game for the player to see and interract with  
  
  // this is the win scene, when the player has complete the game they will repsent with this scene 
      scene("you have win", (time) => {
      add([
        text("win ", { size: 24 }),
        pos(vec2(400, 200)),
        origin("center"),
        color(255, 255, 255),
      ]);

// this is the scene text with in the win scene that allows the player to go back to the main manu 
      add([
        text("press enter to go back to the start menu ", {
        size: 24}),
        pos(vec2(500, 350)),
        origin("center"),
        color(255, 255, 255),
        text
      ]);
// when the player press enter it will go back to the manu menu 
      onKeyRelease("enter", () => {
        go("start");
      })
    });
```

### Challenges



there was a position issue with text ( press enter to go back to the start menu) , i resolved with this  by changing the value used in the function pos()

## Testing

Evidence for testing

### Tests

| Test | Instructions                  | What I expect                                                                                                                                             | What actually happens  | Pass/Fail |
| ---- | ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------- |
|      | run code                      | the portal should appear above the platform                                                                                                               | does what is mentioned | pass      |
| 1    | The portal to the next level  | When the player goes through the portal the player should be taken to the next level                                                                      | Does what is mentioned | pass      |
| 2    | death scene                   | when the player dies in the game a death scene should appear  to let the player know they have died as well as give a option to go back to the start menu | runs as mentioned      | Pass      |

### Evidence

![](<../.gitbook/assets/image (13) (2).png>)

![](<../.gitbook/assets/image (10).png>)

