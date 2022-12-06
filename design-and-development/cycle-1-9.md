# Cycle 10 menu

##

## Design

### Objectives

For this cycle i aim to add a main menu where the player will load into in order to start the game. The menu will have two option, a option  to start the game or an option that tells the player how to play the game.&#x20;



* [x] Adding menu



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

| Test | Instructions | What I expect | What actually happens | Pass/Fail |
| ---- | ------------ | ------------- | --------------------- | --------- |
| 1    |              |               |                       | Fail      |
| 2    |              |               |                       | Pass      |

### Evidence
