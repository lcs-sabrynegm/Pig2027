#   Pig 
 
## How to play
 
1. Click roll and decide when to stop rolling when you're satisfied, click hold, but try not to roll a one**.
2. If you want to risk it, press steal for a 50% chance to steal half you're opponents points, 25% chance to lose half your points, or a 25% chance to lose automatically
3. Your friend repeats the first two steps during their turn.
4. First to 100 points wins.
 
## What I added
 
- Added an actual ending when a player reaches one hundred featuring a symbol and message, I also disabled rolls/holds when they win
- added a new button, the steal button, which has a 50/50 chance of either stealing half the opponents points or losing half your points
- added messages for the new steal button

### How it works
the steal button works essentially by generating either a one or a two in a constant titled fiftyfifty, i used a constant instead of two randomness pieces to save having to duplicate code, if a one is generated then a nested if statement is run resulting in another constant called losing fiftyfifty to run for the losing side meaning there is a 25% chance the current player loses half their points(randomness logic rolled a 1 then a 1), and a 25% chance they lose the entire game by stealing (randomness logic rolled a 1 then a 2).  However if a two is generated the other if statements run resulting in the current player stealing half the other player's points (randomness logic rolled a 2). The turn is switched after the button is pressed.
Design choice: I added a 25% chance of losing if steal is pressed so that there is larger consequences for pressing the buttons and it isnt as wecoming however still worth pressing in dire situations because of the 50% success rate.
I added an ending number constant being 100 and it is used to check if the game is over symbols are changed and so is the message, buttons are also deactivated when the game ends.
I added a bigHeader variable for the header that shows who's turn it is, it is now blank when someone wins and it uses returns.
### Testing
testing if 100 is actually winning number

|Chosen Input|What should happen|What did happen|
|---|---|---|
|3|should take 34 rolls to win|it took 34 rolls|
|5|should take 20 rolls to win|it took 20 rolls|
|1|should never win|never won|
|1|should never win|never won|

all tests passed meaning the game actually ends when reaching 100

| chosen input | what should happen | what happend |
| --- | --- | --- | --- |
| opponent starts at 50 points, fiftyfifty is set to 1 |current player should lose half their points |  current player lost half their points | opponent starts at 50 points, fiftyfifty is set to 2 |
| current player should steal 25 points |  current player stole 25 points | |  |
both tests pass meaning all steal outcomes do what they are meant to

Testing all steal possibilities
| Test | Chosen Input | What Should Happen | What Did Happen |
|---|---|---|---|
| Player 1 wins the steal | Player 1 starts at 20, Player 2 at 50; flip fixed at 2; Player 1 clicks Steal | Player 1 score goes to 45; Player 2 score goes to 25 | It works! |
| Player 1 loses steal and loses half their points | Player 1 starts at 21, Player 2 at 50; flip fixed at 1; losing flip fixed at 1 | Player 1 score goes to 10; Player 2 score stays at 50 | It works! |
| Player 1 loses steal and loses the game | Player 1 starts at 5, Player 2 at 99; flip fixed at 1; losing flip fixed at 2 | Player 1 score stays the same; Player 2 score goes to 100 and wins | It works! |
| Stealing on the winning edge | Player 1 starts at 80, Player 2 at 40; flip fixed at 2 | Player 1 steals exactly 20 points and wins the game | It works! |
all steal possibilities work as intended
## Credits 
- The starting game was written by Mr. Gordon.
- Chatgpt was used to write and understand changes in disabling rolls/holds and figuring out how to change button color
- Symbols off of SF symbols
- claude to help create and understand bigHeader logic


