# 2.2.1 Cycle 3

##

## Design

### Objectives

the objective of this cycle is to add a stop watch to the game where by the player can see how long it takes to complete the level as well as compete against themselves to improve the time taken to complete the level . Another objective to i will be completing this cycle is to add pits traps and spikes to the game in which if the player comes in contact with the any of these dangers the player will lose a health point or risk losing the game . &#x20;

* [x] add a stopwatch
* [x] obstacles ( pits, traps, and spikes )

### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use                                                                                                                               |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| timer ()      | this variable is used to add the stopwatch function                                                                               |
|   danger      | this variable is used in a way that if the player comes in contact with spikes or trap or a bot it will lead the player to death  |

### Pseudocode

```
 const timer = add([
		text("stopwatch:  0 "),
		pos(3, 86),
		fixed(),
    scale(0.50),
		{ time: 0, },
	])

	timer.onUpdate(() => {
		timer.time += dt()
		timer.text = " stopwatch" + timer.time.toFixed(2)
	})
```

## Development

### Outcome

### Challenges

one of the challenges that i faced during the implantation of the stopwatch is correctly positioning the stopwatch meter on the screen so that the player can see the stopwatch easily. I overcame this by adjusting the size of the font that was used and adjusting the positions of it as well as  placing the stopwatch below another  instrument that was displayed to the player &#x20;

## Testing

i test if the spike worked by  with a spike this resulted in the players death&#x20;

### Tests

| Test | Instructions     | What I expect                                                                                                                                                                                                     | What actually happens                                                                                                                                 | Pass/Fail |
| ---- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | added my spikes  | the spikes will function in a manner where when the user going in contact with  the spikes the player will take damage which will lead to death if the player comes in contact with it in more than one occasion  | the spikes are add successfully  however when the player comes in contact with the spikes the player does not take any damages to the players health  | Fail      |
| 2    | stop watch       | when the player starts the game the stopwatch will start and once the player has completed he game by finishing the level the stop watch will stop                                                                | the stopwatch worked as expected                                                                                                                      | Pass      |

### Evidence



<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
