# Cycle 4: Stopwatch

##

## Design

### Objectives

The objective of this cycle is to add a stopwatch to the game whereby the player can see how long it takes to complete the level as well as compete against themselves to improve the time taken to complete the level. Another objective I will be completing this cycle is to add pits traps and spikes to the game in which if the player comes in contact with any of these dangers the player will lose a health point or risk losing the game. &#x20;

* [x] Have a working stop watch start the moment the player starts the game&#x20;
* [x] Be able to display the stopwatch on the player screen during game play&#x20;



### Usability Features

Stopwatch - The stopwatch should be simple to read. Additionally the stop watch should not obstruct the player view of the game the stop watch will be in a corner to prevent this.

### Key Variables

| Variable Name | Use                                                                                                                                                                   |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| stopwatch ()  | This variable is used to add the stopwatch function                                                                                                                   |
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

An overall outcome was that the stopwatch was successfully added to the game. I was able to do this with the knowledge I obtained from doing the coin system in cycle 2. I first created a viable that will store the stopwatch time as it counted it which i named stopwatch.time , whilst researching the way to add a stopwatch to my game i discovered that kbaoom.js already as a stopwatch function build in which was under the function name dt() this made it simple and made it more efficient for me due to the amount of time i saved . Once that stopwatch.time function was created I turned my attention to presenting it to the player. I did this by creating a viable function called stopwatch. text this contain the string "stopwatch " and the previous mention stopwatch.time function

```javascript
  stopwatch.onUpdate(() => {
    stopwatch.time += dt()
    stopwatch.text = " stopwatch" + stopwatch.time.  })
```

there is not much different between when adding the output read out function for the coins and the output read out for the stopwatch. the only only difference is that the inital value of stopwatch is 0 as well as the scale of the text being small then the text for the coin this was also do with the funciton scale() and lastly the position of stopwatch is place above the coin  system this to prevent the player from being obstructed by the counting stopwatch.&#x20;

```javascript
  const stopwatch = add([
    text("stopwatch : 0 "),
    pos(3, 86),
    fixed(),
    scale(0.50),
    { stopwatch: 0 },
  ])



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

![](<../.gitbook/assets/image (25).png>)

