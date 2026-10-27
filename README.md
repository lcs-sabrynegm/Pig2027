#  # Pig
 
You against a friend. Finish your turn and it switches to your friend's turn.
 
## How to play
 
1. Click roll and decide when to stop rolling when you're satisfied, click hold, but try not to roll a one**.
2. If you're want to risk it press steal for a 50% chance to steal half you're opponents points or lose half your points
3. Your friend repeats the first two steps during their turn.
4. First to 100 points wins.
 
## What I added
 
- Added an actual ending when a player reaches one hundred featuring a symbol and message, I also disabled rolls/holds when they win
- added a new button, the steal button, which has a 50/50 chance of either stealing half the opponents points or losing half your points
- added messages for the new steal button

### How it works
the steal button works essentially by generating either a one or a two in a constant titled fiftyfifty, i used a constant instead of two randomness pieces to save having to duplicate code, if a one is generated then a couple if statements run resulting in the current player loses half thier points but if a two is generated the other statements run resulting in the current player stealing half the other player's points. The turn is switched after the button is pressed.
I added an ending number constant being 100 which checks 
### Testing
testing if 100 is actually winning number
|  Chosen Input |  What should happen | What did happen |
| --- | --- | --- |
|  3|  should take 34 rolls to win |  it took 34 rolls |
|  5|  should take 20 rolls to win |s it took 20 rolls |
|  1|  should never win | never won |
all tests passed meaning the game actually ends when reaching 100

| chosen input | what should happen | what happend |
| --- | --- | --- | --- |
| opponent starts at 50 points, fiftyfifty is set to 1 |wcurrent player should lose half thier points |  current player lost half thier points | opponent starts at 50 points, fiftyfifty is set to 2 |
| current player should steal 25 points |  current player stole 25 points |  |  |
both tests pass meaning all steal outcomes do what they are meant to
## Credits 
- The starting game was written by Mr. Gordon.
- Chatgpt was used to write and understand changes in disabling rolls/holds and figuring out how to change button color
- Symbols off of SF symbols


