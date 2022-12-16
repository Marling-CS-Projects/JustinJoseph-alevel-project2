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

since the premise of the moving platform is to have platforms to move from left to right and back i decided to save time by using the same code that was used for the enemy cycles with the only alteration by that the spped with it moves and the distanct as well , if you were to comparte the two componet  you use find that the moveing has a fast speed set at 100 this is to help the player to beat the clock that other wise the player could find that by not using the moving platfrom they could complete the level faster, an addaitoal feature that the enemy does not have is a distant compoet to the moving platfrom this would limit the area the platform can cover this is to prevent the moving platfrom going of the game screen. This enabled me to create the moving platform function (mp  for the variable name).&#x20;

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

Once the main alteration has been made to make it a moving platform function i procced to draw what the component would look like on the left it is desgin to resemble a acid bath whilst on the right is the stanard platform but made short width wise. i designs are made to be regonible and keep in line with pegi ratings of 12 .&#x20;

![](<../.gitbook/assets/image (15).png>) ![](<../.gitbook/assets/image (4).png>)



After the design were created it was upload the kaboom and giving a image address whilst i proceed to give each component its own tag. which would be to refer to through out the cycle

```
loadPedit("platform3", "sprites/platform3.pedit");
loadPedit("acid", "sprites/acid.pedit");
```



This is the stage where both of the component take up their roles with in the game . For the platform it was given that the  varible name j as other letter for the platform was used up and this enbale it to be easly differentiable  from the other platform when it come to add it to the level. Once the componetn was given  a viarble name the funciton area() and soild() was given as mentioin in perious cycles the area() enblae the platform to have a hitbot which enbale the player to make contact with the platfrom  whilst solid() enabled the player to stand on it with out falling though. The last funciton that is need to be talked about is the function called mp() after making the alteration to enemy code , this is mentioned above,  to summaries it  allow the platfrom to move from left rigth and back when all incporatied all togehter is has succesufl worked , allow the player to get from a point a to b when it is to far jump or doble jump .

```javascript
  "j": () => [
    sprite("platform3"),
    area(),
    solid(),
    mp(),
    origin("bot"),
  ],
```

As part  the sucess certia it was meniton to have different types of obstcle for the player to over come after seeing the protenical of a moving platform i descided to create a obstcle equalent of that this lead to create a the moving acid bath in which that if the player fall in or coming in contact of it the player dies quickly. To be efficient i use the code i cretaed the for moving patform ( shown abvoe ) and procced to add and alter the code . With two miner cahner be that the vaible has change from j to a ( i found as is apporatie for this as well as it not being used ment that it was easy to ideieifty what it\`s role is ) . the second miner change being that i have add the acid bath in the dnager cagtory that is used for the obstcles in cyles 3 and the enemy in cyle 5 this mangaged to stremline the process , by using the tag "danger"  it allow the game to identifty that when player comes in contact with the acid bath the game should end thus allowing me to use the player.Oncollide to achive this goal&#x20;

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
