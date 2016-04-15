## Stick Hero

### Game Description

In this game, the player need to hold on the screen such that the stick that the man is holding increase its length such that the stick can be used to across the gap between two black pillars.

**Playstore Link:** [Stick Hero](https://play.google.com/store/apps/details?id=com.ketchapp.stickhero&hl=en)
 
**Difficulty Level:** Moderate

You can see a demo video of the working of this game at the following link: https://youtu.be/Na2GrGcEe9Q

{% if output.name == "ebook" %}
<div class="row" style="text-align:center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/Na2GrGcEe9Q" frameborder="0" allowfullscreen></iframe>
</div> 
{% endif %}

### Overview

The black pillars are detected using image processing and the distance between them is calculated. This distance is converted to time by using a linear equation. The screen is touched by using the adb tool library.

### Requirements

- An Android Device with the ‘Stick Hero’ game installed in it.
- Single Strand Wires, Coins, Relays are used to simulate the touch on the capacitive touch screen of phones and tablets.
- Arduino is used to control the duration of the touch.
- Matlab: Used for Image Processing.
- Arduino IDE: For programming the Arduino.
- IP Cam: It is an android app which enables us to use our smartphones cam as a web cam. You can use a webcam directly if you have a good quality webcam available.

### Connection Diagram

![ConnectionDiagram](/Images/stickhero-diagram.PNG)

### Block Diagram

![BlockDiagram](/Images/methods-3.png)

### Tutorial

Here's the step-wise tutorial to automate the game using approach 3. The source code is avaiable [here](https://github.com/GameAutomators/StickHero).

#### Step 1: Detecting the black pillars

This is done by using Matlab. The image that is captured from the IP Cam is processed and the locations of the black pillars are determined. The distance between the black pillars is calculated and the corresponding data is sent to the Arduino through serial communication.

#### Step 2: Determining the duration of the touch

Based on the data arrived from Matlab, the duration of the touch is adjusted such that the stick exactly falls on the adjacent pillar.

#### Step 3: Simulating Touch

Relays are directly connected to the output pin of the Arduino. It is equivalent to a touch if the voltage given is high as there is a path for the current to flow to the ground. It is equivalent to not touching if the voltage given is low.

### Conclusions

This way, stick hero game can be automated. If setup properly, the system plays the game forever.