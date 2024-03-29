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

An overall outcome was that the stopwatch was successfully added to the game. I was able to do this with the knowledge I obtained from doing the coin system in cycle 2. I first created a variable that will store the stopwatch time as it counted in which i named stopwatch.time. Whilst researching the way to add a stopwatch to my game i discovered that kbaoom.js already as a stopwatch function build in which it was under the function name dt() this made it simple and made it more efficient for me due to the amount of time i saved . Once that stopwatch.time function was created I turned my attention to presenting it to the player. I did this by creating a variable function called stopwatch. text this contain the string "stopwatch " and the previous mentioned stopwatch.time function

```javascript
// this is the code used for the stop watch   
  stopwatch.onUpdate(() => {
    stopwatch.time += dt()
    stopwatch.text = " stopwatch" + stopwatch.time.  })
```

there is not much different between when adding the output read out function for the coins and the output read out for the stopwatch. the only only difference is that the initial value of stopwatch is 0 as well as the scale of the text being smaller then the text for the coin this was also done with the function scale() and lastly the position of stopwatch is place above the coin  system this to keep it simple and clean and easy for the player to find it.&#x20;

```javascript
 // this is the code used to postion the stopwatch in the game  
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

One of the challenges that I faced during the implant of the stopwatch is correctly positioning the stopwatch meter on the screen so that the player can see the stopwatch easily. I overcame this by adjusting the size of the font that was used and adjusting the positions of it as well as placing the stopwatch below another instrument that was displayed to the player. Additional one challenge i am still facing is one where there is no space between the word "stopwatch " and the counter .i still yet to see a fix to this solution i may be a simple fix.

## Testing



### Tests

| Test | Instructions        | What I expect                                                                                                                                       | What actually happens                                                                                                | Pass/Fail |
| ---- | ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | --------- |
| 1    | stopwatch appearing | when player start the game the stopwatch show appear in the designated location                                                                     | The stopwatch appears in the designated location however the when recording time it does not separated from the text | fail      |
| 2    | Stopwatch working   | When the player starts the game the stopwatch will start and once the player has completed he game by finishing the level the stop watch will stop. | The stopwatch worked as expected.                                                                                    | Pass      |

### Evidence

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

