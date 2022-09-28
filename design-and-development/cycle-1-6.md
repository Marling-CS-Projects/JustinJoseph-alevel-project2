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
// death 
if player fall for 1000(
 death scene
 )
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

```
// Some code
```
