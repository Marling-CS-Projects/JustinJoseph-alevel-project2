# cycle 9 moving platform

##

## Design

### Objectives

For this cycle, I aim to add moving platforms to the game as my first priority. The function of the moving platform is to move a platform from left to right within a given space in the level, as part of the function of the moving platform the player will be able to step, run or jump onto the platform and will be able to get off it or jump from it to another platform.&#x20;

Another objective for this cycle is to add an acid bath. The acid bath uses the same function as the moving platform but instead, if the player comes in contact with the acid bath it will result in the death of the player. By adding these components to the game I believe it adds to the gaming experience as it adds a scene of danger to the game which the player will have to overcome.&#x20;



* [x] Add moving platforms  &#x20;
* [x] Acid bath&#x20;





### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use                                                                                                                         |
| ------------- | --------------------------------------------------------------------------------------------------------------------------- |
| mp            | The use of mp is to affect the behaviour of moving platforms left and right between specific points.                        |
|  solid()      | By using this variable it enables the platform to become a solid object which can enable the player to jump on and off it.  |

### Pseudocode

```
```

## Development

### Outcome

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions | What I expect | What actually happens | Pass/Fail |
| ---- | ------------ | ------------- | --------------------- | --------- |
| 1    |              |               |                       | Fail      |
| 2    |              |               |                       | Pass      |

### Evidence

```javascript
function mp(speed = 100, dis = 10, dir = 1) {

  return {
    id: "mp",
    require: ["pos", "area",],
    add() {
      this.on("collide", (obj, col) => {
        if (col.isLeft() || col.isRight()) {
          dir = -dir
        }
      })
    },
    update() {
      this.move(speed * dir, 0)

    },
  }
}
```

```javascript
  "j": () => [
    sprite("platform3"),
    area(),
    solid(),
    mp(),
    origin("bot"),
  ],
```

```javascript
  "a": () => [
    sprite("acid"),
    area(),
    solid(),
    mp(),
    origin("bot"),
    "danger"
  ],
```

```javascript
  player.onCollide("danger", () => {
    go("lose")
  })
```

<figure><img src="../.gitbook/assets/image (11) (1).png" alt=""><figcaption><p>the image above with the rectangular block represents the move platform </p></figcaption></figure>

&#x20; &#x20;

<figure><img src="../.gitbook/assets/image (10) (1).png" alt=""><figcaption><p>the image above with the green rectangle with a black rim represent the acid bath </p></figcaption></figure>
