# Shimon 2.0 Gestures

### Instructions for Use 

1. Open Songs/intoyourmind.maxpat in Max. Besides the patch, you should also see a simulator window of a tiny Shimon! If you don't, the next step should fix this. 

2. Make sure the directory is added to MaxMSP File Preferences, and reopen the patch
 	- Options > File Preferences

3. There is a comment that says "VIPs edit here and below" - this is the only part of this patch you should edit. 

4. The sel object specifies beats of the song where gestures start
You can make your own gesture and attach it to one of the **sel** outputs to have it triggered at that measure. 

5. A very basic gesture example is to the left of **sel**. Click the button with a circle (called a **bang**) to see what it does on the Shimon simulator.

6. Some more complicated examples of gestures are attached to sel already, like **rjs.3directionbow**. You can double click them to see how they work. 

7. To create your own gesture in a nice box like this (a subpatch), you can create a new object with n and then call it **p myNewGesture** (the p is necessary, but you can name it anything)
	- It will need one inlet for an incoming **bang** - create this by typing n for a new object and then call it **inlet**. It will transform into a 1 and a down-arrow. 
	- You can save your subpatch so you can share it with the group! Save it starting with your initials. 

8. You have access to the following gesture commands:

**rjs.basePan [position] [velocity]**
- Min position: -1.25
- Max position: 1.25
- Default: 0
- Max velocity: 5

**rjs.neckPan [position] [velocity]**
- Min position: -1.1
- Max position: 1.1
- Default: 0
- Max velocity: 25

**rjs.neckTilt [position] [velocity]**
- Min position: -0.5
- Max position: 0.9
- Default: 0
- Max velocity: 15

**rjs.headTilt [position] [velocity]**
- Currently no max and min position
- Max velocity: 20

9. To execute a gesture command, send a **bang** to a **message** and connect the message to the input of the gesture (like the examples). You can create a bang by pressing **b** and a message by pressing **m**. The message should contain the arguments expected by the gesture command (position and velocity). 

10. **Delay [time in ms]** sends a **bang** after a specified number of milliseconds has passed. (You don't actually write the square brackets, you might write **delay 300**)

11. You can play the song by selecting a beat number you want to start at in the sliding bar, and then pressing the big square with an X (**trigger**) to start playing from there. Press the **trigger** again to stop the song. 


Notes:

- We have control over Shimon's eyebrows, but they are currently not in the model, so we'll ignore them for now. 



### Gesture List (found in the gestures folder)
Gestures contains all created gestures:
These are:

| Name| Description | Input |
| --------------	|----------------	|---------------- |
| rjs_3directionbow     	| Bow            	|bang  |
| rjs_evil     	| Side to side evil       	| bang |
| rjs_lowbeat     	| Side to side evil       	| bang |
| rjs_samples     	| Collection of small gestures, can be broken out when needed     	| - |
| rjs_sway     	| Side to side evil       	| toggle |


### Useful Objects in Max
- cycle
- delay
- t (for order of operations)

For random/stochastic
- urn
- drunk
- random
