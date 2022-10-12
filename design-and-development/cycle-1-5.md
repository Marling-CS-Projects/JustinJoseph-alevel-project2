# Cycle 6 exit door

##

## Design

### Objectives

the objective of this level is to add a exit door for the player . Onced the player has passed though the door the level is completed and if the player choses to they can be  taken to the level after which going though that door the level is fully completed .

* [x] add a exit door
* [x] takes the player to the next level  &#x20;
* [x] once the player has completed all of the levels the win scene will appear   &#x20;





### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use                                                                                                                                                                                        |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| win scene     | the variable is used to show the player the win scene if the player has reached the exit of the level                                                                                      |
|  add          | this is to include objects, text and components to the game . in this case it is to add text and  position it on the screen for when the player win the level (by getting to the portal )  |

### Pseudocode

<pre><code><strong>if player collide with exit (
</strong><strong> go to next level
</strong><strong> )</strong></code></pre>

## Development

### Outcome

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions                  | What I expect                                                                         | What actually happens  | Pass/Fail |
| ---- | ----------------------------- | ------------------------------------------------------------------------------------- | ---------------------- | --------- |
| 1    | the portal to the next level  | when the player goes through the portal the player should be taken to the next level  | does what is mentioned | pass      |
| 2    |                               |                                                                                       |                        | Pass      |

### Evidence

```javascript
  "@": () => [
    sprite("portal"),
    area(),
    solid(),
    origin("bot"),
    "exit"
  ],
```

```javascript
  player.onCollide("exit", () => {
    go("win")
  })
```

```javascript
    scene("win", (time) => {
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

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
