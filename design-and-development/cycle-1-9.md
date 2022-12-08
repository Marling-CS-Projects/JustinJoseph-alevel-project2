# Cycle 10 menu

##

## Design

### Objectives

For this cycle I aim to add a main menu where the player will load into in order to start the game. The menu will have two options, an option to start the game and an option that tells the player how to play the game by clicking on said option.



* [x] Create a menu seen for the player to see
* [x] Give the player the option between starting the game or to see the controls and the objective of the game&#x20;
* [x] Give the player the ability to click and select the option they wish to use&#x20;



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |
|               |     |

### Pseudocode

```
```

## Development

### Outcome

To start the off my development cycle i proceed to create  a scene for my menu with a welcoming title and two option, to start the game or a option on how to play the game. Once i created the welcoming menu i went on to branching the manu out such that if the player clicks start it take will the player directly to the game and if the play click the other option the player is taken to another scene with instruction on how to the play the game ( this is shown with the code below). To add simplity to the menu all of the titles and option is done in large fount to make it easy to read.

```javascript
scene("start", () => {

  


  add([
    text("Click HERE to start!", { size: 24 }),
    pos(vec2(400, 200)),
    origin("center"),
    area(),
    "Start"
  ]);


  add([
    text("How to play HERE", { size: 24 }),
    pos(vec2(400, 300)),
    origin("center"),
    area(),
    "Start01"
  ]);


  onClick("Start01", () => {
    go("tr")
  })

  onClick("Start", () => {
    go("game")
  })

});

   
```

Once I had created the main menu, I proceeded to create a scene for the second option ("how to play the game"). Since i was limited to the size of the game frame i aim to keep the objective of the game and the control simple to understand ( this is shown in the image below ). whilst testing the code to see any issues, i encountered issues with the  size of the text present during the game being run as well as the text being misaglihted. I resolve this issues by adding a sizing function ("size: 24 ") to the code that is repenziedning the text whilst for the misaligning issue i proceed to add a position function (''pos(vec2(200, 100)),") that enabled me to control where the text is positioning with x and y coordinates. Finally I added back to the exit button enabling the player to go back to the main menu form the how to play scene , clicking upon on the exit button was an improvement over the previous method of refreshing the page.

```javascript
  scene("tr", (time) => {
      add([
        text("Controls:", { size: 24 }),
        pos(vec2(200, 100)),
        origin("center"),
        color(255, 255, 255),
        text
      ]);

       add([
        text(" A = Move Left \n D = Move Right \n   Spacebar = Jump/Double jump   ", { size: 24 }),
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
```

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions                                                          | What I expect                                                                                                                                                                       | What actually happens                                                                                                                                                   | Pass/Fail |
| ---- | --------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    |  running the code                                                     | when running the code the game should load the player in the menu screen and provide the options play the game and how to player the game and allow the player to click the options | the code as ran as expected                                                                                                                                             | pass      |
| 2    | test if the game take to player to the intend option                  | when the player click on a option on the start menu the player should be taken to intended option                                                                                   | when the player clicks a opotion it takes the player ot the wrong intneded place e.g when the player click " to play" the menu take the playe to how to play the game"  | fail      |
| 3    | test if the game take to player to the intend option (second attempt) | when the player click on a option on the start menu the player should be taken to intended option                                                                                   | the player got the intended destination when the a option is clicked. I manged to fix the issue by changing the scene that was being used                               | pass      |
| 4    |                                                                       |                                                                                                                                                                                     |                                                                                                                                                                         |           |

### Evidence
