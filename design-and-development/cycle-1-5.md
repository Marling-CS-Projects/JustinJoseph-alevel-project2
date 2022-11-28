# Cycle 6 exit door

##

## Design

### Objectives

The objective of this level is to add an exit door for the player. Once the player has passed through the door the level is completed and if the player chooses to they can be taken to the level after which going through that door the level is fully completed.

* [x] Add an exit door
* [ ] Takes the player to the next level  &#x20;
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
| 1    | The portal to the next level  | When the player goes through the portal the player should be taken to the next level  | Does what is mentioned | pass      |
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

<figure><img src="../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>
