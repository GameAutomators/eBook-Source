# Introduction to Electronics 

Electronics deals with the use of circuits that involve various electrical components. Everything from the clock you see to find time to the smartphone in your hand connecting you to your friends every second are the applications of it. In this section, we will give a brief overview of the electronics that we need to get started with working on the book.

If you are a beginner, this video series on YouTube is a great way to start- “Building Electronic Circuits” by The Motivated Engineer. It starts off by giving you an overview of the basics of the electronic components generally used and teaches you how to work on some cool projects such as infra red sensors and wearable circuits. Watching and practicing the circuits in the first five videos in this series would give you a decent level of understanding to continue reading the sections below. These videos are optional to watch for people who have worked on electronic circuits before.

Link: https://www.youtube.com/playlist?list=PLmcMMZCV897om7Wuqz882Jdp9lGj9HYHs 

<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PLmcMMZCV897om7Wuqz882Jdp9lGj9HYHs" frameborder="0" allowfullscreen></iframe>

Next, we explain a simple circuit that is used very commonly while trying to solve mobile games.

### Voltage Divider Circuit

![Voltage Divider Circuit](/Images/VoltageDividerCircuit.png)

A voltage divider circuit is commonly used in many electronic circuits for a wide range of applications including adjusting level of signal, measurement of voltages, etc. It is used in multimeter and wheatstone bridge. It produces an output voltage which is a fraction of the input voltage. The value of the output voltage depends on the values of the resistors used.

The output voltage of the above circuit can be calculated by the following equation.

Vout = ((R2) / (R1 + R2)) * Vin

We will use this circuit in the next chapter when we talk about the Light Dependent Resistor (LDR).

LDR can be used in place of one of the resistors. The resistance of the LDR decreases if the incident light increases, and vice-versa. This change in resistance can be used to produce a change in voltage at the output which is important in many applications. For example, when we use a microcontroller, we can detect the lighting in a room by just measuring the voltage at the output of a voltage divider circuit in which an LDR is used in place of one of the resistors. 
