# Cycle 9: Moving Platform

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

Since the premise of the moving platform is to have platforms to move from left to right and back I decided to save time by using the same code that was used for the enemy cycles with the only alteration by that the speed with it moves and the distance aswell. If you were to compare the two components you find that the moving platform has a fast speed, set at 100, to help the player to beat the clock that otherwise the player could find that by not using the moving platform they could complete the level faster. An additional feature that the enemy does not have is a distant component to the moving platform, this would limit the area the platform can cover to prevent the moving platform going of the game screen. This enabled me to create the moving platform function ("mp" for the variable name).&#x20;

<pre class="language-javascript"><code class="lang-javascript"><strong>// mp = moving platfrom 
</strong><strong>function mp(speed = 100, dis = 10, dir = 1) {
</strong>
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
</code></pre>

Once the main alteration has been made to make it a moving platform function I proceeded to draw what the component would look like on the left it is a design to resemble an acid bath whilst on the right is the standard platform but made short, width-wise. The designs are made to be recognisable and keep in line with PEGI ratings of 12.&#x20;

![](<../.gitbook/assets/image (15).png>) ![](<../.gitbook/assets/image (4).png>)



After the designs were created it was uploaded to kaboom and given an image address whilst I proceeded to give each component its own tag. Which would be to referred to throughout the cycle.

```
loadPedit("platform3", "sprites/platform3.pedit");
loadPedit("acid", "sprites/acid.pedit");
```

This is the stage where both of the components take up their roles within the game. For the platform it was given that the variable name "j", as another letter for the platform was used up, and this enabled it to be easily differentiated from the other platform when it comes to adding it to the level. Once the component was given a variable name, the functions "area()" and "solid()" were given as mentioned in previous cycles. "area()" enables the platform to have a hitbox which allows the player to make contact with the platform whilst solid() enabled the player to stand on it without falling though. The last function that is needed to be talked about is the function called "mp()" after making the alteration to enemy code, this is mentioned above. In summary, it allows the platform to move from left to right and back when all incorporated together it has successfully worked, allowing the player to get from a point a to b when it is to far jump or double jump.

```javascript
  "j": () => [
    sprite("platform3"),
    area(),
    solid(),
    mp(),
    origin("bot"),
  ],
```

As part of the success criteria it was mentioned to have different types of obstacle for the player to overcome. After seeing the potential of a moving platform, I decided to create an obstacle equivalent of that which led to the creation of the moving acid bath in which that if the player falls in or comes in contact with it, the player dies quickly. To be efficient I used the code I created for the moving platform (shown above) and proceeded to add to and alter the code. With two minor changed being that the variable has change from "j" to "a" (I found it appropriate for this as well as it not being used meaning that it was easy to identify what its role is). The second minor change being that I have added the acid bath in the danger category that is used for the obstacles in cycle 3 and the enemy in cycle 5. This managed to streamline the process, by using the tag "danger"  it allows the game to identify that when the player comes in contact with the acid bath the game should end thus allowing me to use the "player.Oncollide" to achieve this goal.&#x20;

```javascript
  "a": () => [
    sprite("acid"),
    area(),
    solid(),
    mp(),
    origin("bot"),
    "danger"
  ],
  
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

| Test | Instructions          | What I expect                                                                                                                                    | What actually happens                                                                                                                                                                                                                                                                               | Pass/Fail |
| ---- | --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Run code              | When the platforms move they should move from left to right and once they come in contact with the solid platform they should go the other way   | The platform works but not in the expected way. This is because when the platform moves from left to right it goes through the solid platfrom instead of bouncing back and going the way it came                                                                                                    | Fail      |
|      |                       | When the platform moves, they should move from left to right and once they come in contact with the solid platform, they should go the other way | After the first test failed I went into the code of the moving platform I found that I did not include the solid() function which allows the moving platform to be known as a solid. Once it was added, the platform goes left and right as expected                                                | Pass      |
|      | Run code with player  | For this test, I wanted to see how the platform interacts with the player                                                                        | Through the test I found that there is bug with the platform. In which the player can make contact with the side of the moving platform as a substitute for the solid platform and the moving platform would think it had made contact with a solid platform.                                       | Fail      |
|      | Run code with player  | For this test, I wanted to see how the platform interacts with the player                                                                        | When doing the last test I found a bug (mentioned in test 3). However whilst conducting other tests on the moving platform the result of it was fine as it allowed the player to jump on it as well move around on it with out causing any direct issue to the moving platform whilst in operation  | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption><p>the image above with the rectangular block represents the move platform </p></figcaption></figure>

&#x20; &#x20;

<figure><img src="../.gitbook/assets/image (10) (2).png" alt=""><figcaption><p>the image above with the green rectangle with a black rim represent the acid bath </p></figcaption></figure>
