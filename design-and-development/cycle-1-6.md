# Cycle 7 death and falling

##

## Design

### Objectives



* [x] add falling death   &#x20;
* [ ] &#x20;add a death scene&#x20;



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use |
| ------------- | --- |
|               |     |
|               |     |

### Pseudocode

```
// falling death 
if player falls below 1000(
 death scene
 )
```

```
if player dies (
  display death scene
  give the option to the player to play again 
  )
```

## Development

### Outcome

i have succssfully had falling death and a death scene to go with it&#x20;

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
// death 
 	player.onUpdate(() => {
		if (player.pos.y >= 2000) {
			go("lose")
		}
	})

  
  player.onCollide("danger", () => {
		go("lose")
  })

    
  player.onCollide("exit", () => {
		go("win")
  })
```

```javascript

 scene("lose", (time) => {
  add([
    text("lose ", { size: 24 }),
    pos(vec2(500, 350)),
    origin("center"),
    color(255, 255, 255),
    text
  ]);
```
