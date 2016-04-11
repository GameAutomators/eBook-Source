## Cars Memory Game

### Game Description

In this game, all the tiles have an image on the other side that you can see when you tap it. At most, only two tiles would turn before turning backwards again. If we flip two tiles which have the smae image, they will disappear. The game ends when all the tiles on the board disappear.

**Playstore Link:** [CarsMemory](https://play.google.com/store/apps/details?id=com.developandroid.android.cars&hl=en)

![Playstore](/Images/cars-memory-1.png) 
![Image](/Images/cars-memory-2.png)

**Difficulty level**: Moderate

### Overview

First, we flip all the tiles and save all the images in a cell in MATLAB. Then we find the histograms of these images and compare them to find which ones are similar. We then tap all the similar images using ADB tool.

### Requirements

- Computer with MATLAB, ADB Tool and required drivers set up.
- An Android Device with the 'Cars Memory Game' installed on it. (Turn on the Developer options for better visualization)
- USB data transfer cable.

### Block Diagram

![BlockDiagram](/Images/BlockDiagram.png)

### Tutorial

Here's the step-wise tutorial to automate the game. The source code is avaiable [here](https://github.com/GameAutomators/cars-memory-game).

#### Step 1: Using ADB Tool to capture screenshot

The following command instantaneously takes the screenshot of the connected device and stores it in the SD card following the specified path.

```MATLAB                    
system(' adb shell screencap -p /sdcard/screen.png ');
```       

The following command pulls it from the SD card of the android device into the working system following the path specified.

```MATLAB
system(' adb pull /sdcard/screen.png ');
```
  
The pulled image is stored in the form of a matrix of pixel values by the MATLAB.                
                
#### Step 2: Image processing

After taking screenshot, we analyse the image using various image processing functions to find the size and number of tiles on the board. All this code is written inside the function `analyseBoard`.

```MATLAB
board = analyseBoard(input);
```

Then, we retrive all the images on back of the tiles by tapping them and storing the image. This code is written inside the function `retriveImage`.

```MATLAB
for a = 1:board.size(1)
    for b = 1:board.size(2)
        tiles{a, b} = retriveImage(a, b, board);
    end
end
```

#### Step 3: Algorithm to Compare Images

We extract the histograms of each of these images and save them in the variable `histTiles`.

```MATLAB
%% Extracting histograms of each image

board.tiles = board.size(1)*board.size(2);
histTiles = cell(board.tiles,1);
for a = 1:board.size(1)
    for b = 1:board.size(2)
        histTiles{b+(a-1)*(board.size(1)+1)} = imhist(tiles{a, b}(:,:,1));
    end
end

```

We find the similarity of two tiles by finding the sum of differences between the histograms.

```MATLAB
%% Finding similarity

differences = 100000*ones(board.tiles);
for i = 1:board.tiles
    for j = i+1:board.tiles
        differences(i,j) = sum(abs(histTiles{i}(20:240)-histTiles{j}(20:240)));
    end    
end

```

The similar position can be found by finding the minimum value of `differences` in each of the rows.

```MATLAB
[val, pos] = min(differences(i,:));
```

#### Step 4: Using ADB Tool to simulate touch

We finally simulate touch on top of the tiles that are similar so that they disappear. We should give a small time gap for the game animation to render.

```MATLAB
system(['adb shell input tap ' num2str(board.centerX(i)) ' ' ...
                               num2str(board.centerY(i))]);
pause(0.3); 
```

### Conclusions

This way, the game is automated. The code has been written in a robust way such that it works for all the levels: easy, medium and hard.