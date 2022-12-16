# Cycle 6: Exit Door

##

## Design

### Objectives

The objective of this level is to add an exit door for the player. Once the player has passed through the door the level is completed and if the player chooses to they can be taken to the level after which going through that door the level is fully completed.

* [x] Add an exit door
* [x] Takes the player to the next level  &#x20;
* [x] Once the player has completed all of the levels the win scene will appear   &#x20;





### Usability Features

&#x20;&#x20;

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

## Development

### Outcome

The first stage of completing this objective was to create a exit door and then add the exit  to the game in the from of a sprite as shown below .

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Once it was added to the game i also imported its file address and provide the protal a tag

```
// Some code
```



```javascript
  "@": () => [
    sprite("portal"),
    area(),
    solid(),
    origin("bot"),
    "exit"
  ],
```

Once the exit was added to the game I wrote a code stating that when the player comes in contact with the exit the game should go to the win scene this is to the indicate to the player that they have completed the level and that player has the option to leave or continue in the game.

```javascript
  player.onCollide("exit", () => {
    go("win")
  })
```

For the final objective of this cycle was to provide the game with a win scene as well as a return to start screen. This is evident in the code below when the player has completed the level the player will be greeted by a win scene. whilst coding for this scene the i had to adjust the position of the " you have win" text which i achieved by using the command "pos(vec2(400, 200))," to move/ adjust the position of the text in the X and Y direction.&#x20;

```javascript
    scene("you have win", (time) => {
      add([
        text("win ", { size: 24 }),
        pos(vec2(400, 200)),
        origin("center"),
        color(255, 255, 255),
      ]);


      add([
        text("press enter to go back to the start menu ", {
        size: 24}),
        pos(vec2(500, 350)),
        origin("center"),
        color(255, 255, 255),
        text
      ]);

      onKeyRelease("enter", () => {
        go("start");
      })
    });
```

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions                  | What I expect                                                                         | What actually happens  | Pass/Fail |
| ---- | ----------------------------- | ------------------------------------------------------------------------------------- | ---------------------- | --------- |
| 1    | The portal to the next level  | When the player goes through the portal the player should be taken to the next level  | Does what is mentioned | pass      |
| 2    |                               |                                                                                       |                        | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (3) (2) (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1) (2) (2).png" alt=""><figcaption></figcaption></figure>
