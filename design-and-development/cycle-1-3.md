# Cycle 4 stopwatch

##

## Design

### Objectives

The objective of this cycle is to add a stopwatch to the game whereby the player can see how long it takes to complete the level as well as compete against themselves to improve the time taken to complete the level. Another objective I will be completing this cycle is to add pits traps and spikes to the game in which if the player comes in contact with any of these dangers the player will lose a health point or risk losing the game. &#x20;

* [x] Add a stopwatch



### Usability Features

&#x20;&#x20;

### Key Variables

| Variable Name | Use                                                                                                                                                                   |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| timer ()      | This variable is used to add the stopwatch function                                                                                                                   |
| fixed         | This is to ensure that the displayed stopwatch counter does not move with the player or go out of frame but instead stays in the same location throughout the levels  |

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

```javascript
  const timer = add([
    text("stopwatch : 0 "),
    pos(3, 86),
    fixed(),
    scale(0.50),
    { time: 0 },
  ])

  timer.onUpdate(() => {
    timer.time += dt()
    timer.text = " stopwatch" + timer.time.toFixed(2)
  })

```

&#x20;

### Challenges

One of the challenges that I faced during the implant of the stopwatch is correctly positioning the stopwatch meter on the screen so that the player can see the stopwatch easily. I overcame this by adjusting the size of the font that was used and adjusting the positions of it as well as placing the stopwatch below another instrument that was displayed to the player. &#x20;

## Testing

I tested if the spike worked by colliding with a spike, this resulted in the player's death.&#x20;

### Tests

| Test | Instructions      | What I expect                                                                                                                                                                                                       | What actually happens                                                                                                                                      | Pass/Fail |
| ---- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | Added the spikes  | The spikes will function in a manner where when the player comes in contact with the spikes the player will take damage which will lead to death if the player comes in contact with it in more than one occasion.  | The spikes were added successfully  however when the player comes in contact with the spikes the player does not take any damages to the player's health.  | Fail      |
| 2    | Stopwatch         | When the player starts the game the stopwatch will start and once the player has completed he game by finishing the level the stop watch will stop.                                                                 | The stopwatch worked as expected.                                                                                                                          | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (2) (3) (1).png" alt=""><figcaption></figcaption></figure>

The image above displays the use of a stopwatch which is fully functional in the top left corner.
