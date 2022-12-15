# Cycle 9 moving platform

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

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

### Tests

| Test | Instructions          | What I expect                                                                                                                                   | What actually happens                                                                                                                                                                                                                                                                            | Pass/Fail |
| ---- | --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------- |
| 1    | run code              | when the platform moves they should move from left to right  and once they come in contact with the sloid platfom they should go the other way  |  the platfrom works but not in the expect way. This is because when the platfrom moves from left to right it goes through the soild platfrom instead of bounsing back and going the way ti came.                                                                                                 | Fail      |
|      |                       | when the platform moves they should move from left to right  and once they come in contact with the sloid platfom they should go the other way  | After the fisrt test failled i went into the code of the moving platfrom i found that i did not include the soild() function which allow the movies platfrom to be known as a solid .once it was add the platfrom goes left and right as expected                                                | pass      |
|      | run code with player  | For this the i want to see how the platfrom interacts wtih the player                                                                           | through the test i found that there is bug with the platfrom. In which that the player can make contact with the side of the moving platfrom as a substitute for the solid platfrom and the moving platfrom would think it had made contact with a solid platfrom.                               | fail      |
|      | run code with player  | For this the i want to see how the platfrom interacts wtih the player                                                                           | When doing the last test i found a bug ( mention in test 3). However whilst conducting other tests on the moving platfrom the rsult of it was fine as it allow the player to jump on it as well move around on it with out couseing any direct issue to the moving platfrom whilst in operation  | pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption><p>the image above with the rectangular block represents the move platform </p></figcaption></figure>

&#x20; &#x20;

<figure><img src="../.gitbook/assets/image (10) (2).png" alt=""><figcaption><p>the image above with the green rectangle with a black rim represent the acid bath </p></figcaption></figure>
