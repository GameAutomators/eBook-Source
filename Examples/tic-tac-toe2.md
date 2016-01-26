# Tic Tac Toe


### Game Description
This is a two-player game. The player and the system get alternative chances to mark their move on the 3x3 grid provided. One who marks 3 linearly oriented squares first, wins the game. If none of the players can do this, the game ends to be a draw. (The system’s move is marked with a circle and the player’s with a cross)

Playstore Link: [Tic Tac Toe](https://play.google.com/store/apps/details?id=com.pinkpointer.tictactoe&hl=en)

![Playstore](/Images/tttps.png) 
![Image](/Images/tttim2.png=186*330)

#### Difficulty level
Moderate

#### Overview
The player starts at center point. The system’s move is identified using Image processing,
We are simply calculating intersecting points for blank, O and X for each one of Nine Cell.
the further move is calculated by the MinMax algorithm and is marked in the concerned box using ADB Tool.
This continues as the algorithm tries to win the game in the best way possible


#### Requirements
- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the ‘Tic Tac Toe’ game installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable.

#### Block Diagram

![BlockDiagram](/Images/BlockDiagram.png)

#### Tutorial
##### Step 1: Using ADB Tool to capture screenshot
The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.
  
  ```                     
system(' adb shell screencap -p /sdcard/screen.png ');
```       

The following command pulls it from the SD card of the android device into the working system following the path specified

```
system(' adb pull /sdcard/screen.png ');
  ```
  
The pulled image is stored in the form of a matrix of pixel values by the MATLAB.
                
                
##### Step 2: Image processing

Once the screenshot is obtained, nine different points in the 9 boxes are chosen and processed as blank, O or X. For this game blank cell Red color value is - 255 (RGB) , O's cell R value is - 105 and X's cell R value is - 248.
<p>Here 0 -> blank, 1 -> system's move and 2 -> player.</p>
<p>Now form a string of 0, 1 and 2's of length 9 which denotes input.</p>
string is formed of grid[1][1] grid[1][2] grid[1][3] grid[2][1] etc.

##### Step 3: Algorithm

Minimax is a decision rule used in decision theory, game theory, statistics and philosophy for minimizing the possible loss for a worst case (maximum loss) scenario. Originally formulated for two-player zero-sum game theory, covering both the cases where players take alternate moves and those where they make simultaneous moves, it has also been extended to more complex games and to general decision-making in the presence of uncertainty.

```python
def maximized_move(self,game):
        ''' Find maximized move'''    
        bestscore = None
        bestmove = None

        for m in game.free_positions():
            game.mark(self.marker,m)
        
            if game.is_gameover():
                score = self.get_score(game)
            else:
                move_position,score = self.minimized_move(game)
        
            game.revert_last_move()
            
            if bestscore == None or score > bestscore:
                bestscore = score
                bestmove = m

        return bestmove, bestscore

    def minimized_move(self,game):
        bestscore = None
        bestmove = None
        for m in game.free_positions():
            game.mark(self.op_mark,m)
        
            if game.is_gameover():
                score = self.get_score(game)
            else:
                move_position,score = self.maximized_move(game)
        
            game.revert_last_move()
            
            if bestscore == None or score < bestscore:
                bestscore = score
                bestmove = m

        return bestmove, bestscore
```

The Algorithm is written in Python. Matlab call the python script with command line argument of input string which returns the best move.
If game overs it returns 9.

``` 
  inputstr = '001002001';
  [status, result] = system(['python tictac.py ' inputstr]);
``` 

##### Step 4: Using ADB Tool to simulate touch
<p>from the result of algorithm tap position is calculated.</p>
The following command taps at the point on the screen with the co-ordinates mentioned as (x, y). This is used to simulate touch at the appropriate points where we want to make a move.

```
system(' adb shell input tap x y ');
```               
