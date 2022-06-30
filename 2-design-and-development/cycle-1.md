# 2.2.1 Cycle 1

## Design

### Objectives

For my first cycle, I aim to set up the code environment that will be used throughout the project with  HTML so that my game can be played on a browser. With my second objective, I aim to insert a shape or object and be able to move the object via a keyboard without issue. &#x20;

* [x] set the game development environment
* [ ] be able to control the character via the keyboard&#x20;
* [x] &#x20;set up the platforms&#x20;

### Usability Features



### Key Variables

| Variable Name | Use                   |
| ------------- | --------------------- |
|               | does something useful |

### Pseudocode

```
kaboom({
  background: [134, 135, 247],
  width: 1000,
  height: 240,
  scale: 2,
});

// load assets
loadPedit("ground", "sprites/ground.pedit");
loadPedit("main guy", "sprites/main guy.pedit");

// add a character to screen
add([
	// list of components
	sprite("main guy"),
	pos(100, 40),
	area(),
])

// level 
const level = addLevel([
	// Design the level layout with symbols
	"@                        ",
	"===================",
], {
	// The size of each grid
	width: 64,
	height: 64,
	// The position of the top left block
	pos: vec2(100, 200),
	
  // Define what each symbol means (in components)
	"=": () => [
		sprite("ground"),
		area(),
		solid(),
		origin("bot"),
	],
	"@": () => [
		sprite("main guy"),
		area(),
		body(),
		origin("bot"),
		"player",
	],
})
```

## Development

### Outcome

### Challenges

Description of challenges

## Testing

Evidence for testing

### Tests

| Test | Instructions  | What I expect     | What actually happens | Pass/Fail |
| ---- | ------------- | ----------------- | --------------------- | --------- |
| 1    | Run code      | Thing happens     | As expected           | Pass      |
| 2    | Press buttons | Something happens | As expected           | Pass      |

### Evidence
