# Cycle 10: Main Menu

##

## Design

### Objectives

For this cycle I aim to add a main menu where the player will load into in order to start the game. The menu will have two options, an option to start the game and an option that tells the player how to play the game by clicking on said option.



* [x] Create a menu seen for the player to see
* [x] Give the player the option between starting the game or to see the controls and the objective of the game&#x20;
* [x] Give the player the ability to click and select the option they wish to use&#x20;



### Usability Features

&#x20;start screen - the main menu will be the first thing the player see when they load in to the game and thus should have a simple , easy to use and welcoming UI

### Key Variables

| Variable Name                  | Use                                                                                         |
| ------------------------------ | ------------------------------------------------------------------------------------------- |
| <pre><code>size:
</code></pre> | the variable is used to control the size of the text when displayed to the player           |
|  add()                         | this varible enable the newly created componet be added to the game and allow it function . |

### Pseudocode

```
scene(

  


  add([
    text("Click HERE to start!", { size}),
    pos(vec2(400, 200)),
    area
    "Start"
  ]);


  add([
    text("How to play HERE", { size}),
    pos((400, 300)),
    area
    "Start01"
  ]);


 
});
```

## Development

### Outcome

To start off my development cycle I proceeded to create a scene for my menu with a welcoming title and two options, to start the game or an option on how to play the game. Once I created the welcoming menu I went on to branching the options out such that if the player clicks start it take will take the player directly to the game and if the player clicks the other option the player is taken to another scene with instructions on how to the play the game (this is shown with the code below). To add simplicity to the menu all of the titles and options are done in large font to make it easy to read.

```javascript
//this is the main manu code the player will see when running the game 
scene("start", () => {

  

// this is the code that allows the player to start the game 
  add([
    text("Click HERE to start!", { size: 24 }),
    pos(vec2(400, 200)),
    origin("center"),
    area(),
    "Start"
  ]);
  
// this is the code that allows the player to see how to player the game 
  add([
    text("How to play HERE", { size: 24 }),
    pos(vec2(400, 300)),
    origin("center"),
    area(),
    "Start01"
  ]);


 
});

   
 
```

With the use of the function "on Click()" it allowed the player to use the mouse to click on the option that will take them to the respective scene.&#x20;

<pre><code>// by using the mouse to click on either of the options it will initiate the code that will take to the chossen scenes
  onClick("Start01", () => {
    go("rules")
  })
<strong>// this leads to the game being started 
</strong>  onClick("Start", () => {
    go("game")
  })

</code></pre>

Once I had created the main menu, I proceeded to create a scene for the second option ("how to play the game"). Since I was limited to the size of the game frame I aimed to keep the objective of the game and the controls simple to understand (this is shown in the image ). Whilst testing the code to see any issues, I encountered issues with the size of the text that presented during the game being run as well as the text being misaligned. I resolved these issues by adding a sizing function ("size: 24 ") to the code that resized the text whilst for the misalignment issue I proceed to add a position function (''pos(vec2(200, 100)),"). This enabled me to control where the text is positioning with x and y coordinates. Finally I added  a exit button enabling the player to go back to the main menu form the how to play scene, clicking upon on the exit button was an improvement over the previous method of refreshing the page.

<pre class="language-javascript"><code class="lang-javascript"> // this is the scene repsented to the player on how to play the game 
   scene("rules", (time) => {
      add([
        text("Controls:", { size: 24 }),
        pos(vec2(200, 100)),
        origin("center"),
        color(255, 255, 255),
        text
      ]);

// this code shows what is being wrtien in the screne as well as the funciton to move the text around 
<strong>       add([
</strong>        text(" A = Move Left \n D = Move Right \n   Spacebar = Jump/Double jump   ", { size: 24 }),
        pos(vec2(260, 200)),
        origin("center"),
        color(255, 255, 255),
        text
        ]); 
       
       add([
        text("Find the portal and enter it. \n Hint: get to the top!", { size: 24 }),
        pos(vec2(360, 300)),
        origin("center"),
        color(255, 255, 255),
        text
        
      ]);
// this code allows the player to exit the rules scene by click on the option 
      add([
       text("Press HERE to exit", { size: 24 }),
       pos(vec2(360, 550)),
       origin("center"),
      area(),
       "main"
       ]);


    
    onClick("main", () => {
     go("start")
    })
    
    });
</code></pre>

## Description of challenges

during the coding for the main menu i faced a challenge that was later resolved. This was when the player click on a option and the menu takes the player to the wrong scene . for example when clicking the " how to play here " it would take the player to the game it self and vice versa . I solved this by swapping the scene names this resulted  in the main menu functioning correctly. &#x20;

## Testing



### Tests

| Test | Instructions                                                              | What I expect                                                                                                                                                                         | What actually happens                                                                                                                                                    | Pass/Fail |
| ---- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------- |
| 1    |  Running the code                                                         | When running the code the game should load the player in the menu screen and provide the options "play the game" and "how to play the game" and allow the player to click the options | the code as ran as expected                                                                                                                                              | Pass      |
| 2    | Test if the game takes the player to the intended option                  | When the player clicks on an option on the start menu the player should be taken to intended option                                                                                   | When the player clicks an option it takes the player to the wrong intended place e.g. when the player clicks "play" the menu takes the player to "how to play the game"  | Fail      |
| 3    | Test if the game takes the player to the intended option (second attempt) | When the player clicks on an option on the start menu the player should be taken to intended option                                                                                   | The player got the intended destination when the correct option is clicked. I managed to fix the issue by changing the scene that was being used                         | Pass      |
| 4    |                                                                           |                                                                                                                                                                                       |                                                                                                                                                                          |           |

### Evidence

<figure><img src="../.gitbook/assets/image (4) (5).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>
