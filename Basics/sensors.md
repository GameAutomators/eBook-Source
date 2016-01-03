# SENSORS
##### 1.Light Dependent Resistor(LDR)

A photoresistor or light-dependent resistor (LDR) or photocell is a light-controlled
  variable resistor. The resistance of a photoresistor decreases with increasing incident  
  light intensity; in other words, it exhibits photoconductivity.

![image]()
##### How it works
A light dependent resistor works on the principle of photo conductivity. Photo conductivity is an optical phenomenon in which the materials conductivity (Hence resistivity) reduces when light is absorbed by the material.
When light falls i.e. when the photons fall on the device, the electrons in the valence band of the semiconductor material are excited to the conduction band. These photons in the incident light should have energy greater than the band gap of the semiconductor material to make the electrons jump from the valence band to the conduction band. Hence when light having enough energy is incident on the device more & more electrons are excited to the conduction band which results in large number of charge carriers. The result of this process is more and more current starts flowing and hence it is said that the resistance of the device has decreased.This is the most common working principle of LDR.

![image1]()
##### How to use??
A LDR can be used to detect black and white regions on the screen.For example,If a black region is detected on the screen the LDR will not receive an intense light and will go in a off state which can be calibrated to do a particular task.


##### Simple Circuit to use a LDR
![image2]()
##### Source code
###### **Declarations**
Here we are going to declare the pins we are going to use
```
// These constants won't change.  They're used to give names
// to the pins used:
const int analogInPin = A0;  // Analog input pin that the potentiometer is attached to
const int analogOutPin = 9; // Analog output pin that the LED is attached to

int sensorValue = 0;        // value read from the pot
int outputValue = 0;        // value output to the PWM (analog out)
```
###### ***Setup***
```
void setup() 
{
  // initialize serial communications at 9600 bps:
  Serial.begin(9600);
}
```
###### ***Loop***
```
void loop()
 {
  // read the analog in value:
  sensorValue = analogRead(analogInPin);
  // map it to the range of the analog out:
  outputValue = map(sensorValue, 0, 1023, 0, 255);
  // change the analog out value:
  analogWrite(analogOutPin, outputValue);

  // print the results to the serial monitor:
  Serial.print("sensor = " );
  Serial.print(sensorValue);
  Serial.print("\t output = ");
  Serial.println(outputValue);

  // wait 2 milliseconds before the next loop
  // for the analog-to-digital converter to settle
  // after the last reading:
  delay(2);
}
```

##### 2.RGB Sensors
The sensor consists of a grid of color-sensitive filters and a sensor array underneath, as shown on the picture below:

![image3]()

Each filter passes light of only one color to the sensor below. A single pixel is constructed out of 4 filters: blue, red, and 2*green. There are twice as many green filters to mimic the physiology of the human eye which is more sensitive to the green light. The signals from the sensors allow us to calculate the RGB values of each pixel describing it's color in terms of the green, blue and red components.
##### How to do it??
Suppose you have a sensor that can see many different colors, such as a ***photoresistor***. How would you use this sensor to detect red apples vs. green apples? Well, consider brightness comparisons.
Red apples reflect red light but absorb green light. Green apples reflect green light but absorb red light.
If you shine a red light (such as from a red LED) on both apples, the red apple will reflect much more light than the green apple. As such, the apple that appears the brightest to your sensor will be the red apple. If you shine green light from a green LED on both apples, the green apple will appear the brightest.
Suppose you had some M&M's and you wanted your robot to tell the difference between the blue, green, yellow, and orange candies. How would you do this? Well, get a blue LED, a green LED, and a red LED. Then shine each onto the M&M's, one light at a time, and record the brightness values.
Obviously, the blue M&M's will read the highest brightness values when the blue LED is turned on, but very low values otherwise. The green and the yellow M&M's can be detected in a similar manner. So how do you tell the difference between the yellow and the orange M&M? Well, the orange one is closer to red in the light spectrum, and as such will reflect more red light than the yellow one.

##### Build a simple circuit
The circuit is really simple. First we will look at the RGB LED half of the sensor. It is simply a common cathode RGB LED connected to pins 2,3, and 4 of the Arduino with a 220 ohm resistor going out to ground. This will allow us to turn each of the LEDs within the package on and off individually when we need to.


![image4]()

On the other side of the circuit we have a Cds photocell being fed 5 volts from the arduino. combined with the resistor going out to ground this effectively creates a voltage divider which allows us to read a changing analog value on analog pin 0.

##### Source code

Open up the Arduino environment, and create a new sketch by clicking File - New. For those that don`t want to follow along, I have included the code as a text file. Copy/Paste it into a new sketch in Arduino, and you are good to go.

###### **Declarations**

The beginning of a sketch is where we make our declarations, so type the following code into the environment window.

```
// Define colour sensor LED pins
int ledArray[] = {2,3,4};
        // boolean to know if the balance has been set
boolean balanceSet = false;
       //place holders for colour detected
int red = 0;
int green = 0;
int blue = 0;
       //floats to hold colour arrays
float colourArray[] = {0,0,0};
float whiteArray[] = {0,0,0};
float blackArray[] = {0,0,0};
//place holder for average
int avgRead;
'//' is reserved for denoted comments, therefore you do not need the text on lines that begin with '//' for the sketch to work.
```
The rest of it are some names that we are giving to some placeholders, and the declarations for what kind of data they will contain.

As you can see, we start by setting up an array to hold the pin numbers. These correspond to the pins that the different colour LEDs are connected to on the Arduino.

Next we declare a Boolean value to check whether or not balancing has been performed. A Boolean value is something that returns true or false.

We go on to create some place holders for the colour values, and some arrays to use for holding the scan data and balancing the detected colour.

###### **Setup**
The next step in creating an Arduino sketch is to write the setup function. Setup is run when the Arduino first boots up, so this is where we tell the Arduino what how we want to use the pins and setup other features that we may need such as serial communication.

Type the following below the code that you just entered.
```
 void setup()
          {
  //setup the outputs for the colour sensor
  pinMode(2,OUTPUT);
  pinMode(3,OUTPUT);
  pinMode(4,OUTPUT);
 //begin serial communication
 Serial.begin(9600);
 }
 ```
 Not much to this section. Here we are just telling the Arduino that we intend on using pins 2,3,and 4 as outputs. This is neccessary if we want to light our LEDs...and we do, if only very briefly.

The next part is to tell the Arduino that we intend to make use of the serial port, and that it should be opened and ready to communicate at the baud rate specified (in brackets).


##### **Loop**
The loop function is typically where the magic happens in an Arduino. It is the code that is run over and over again once the Arduino is booted and setup has been passed through. Put the next bit of code under your setup function.


```
void loop()
{
           checkBalance();
	checkColour();
	printColour();
	}
 
 ```
 Okay at first glance it looks like there really is not much there. But these are each calls to private functions. For some projects I find this type of approach works well. It makes it easier to read (I think) as each block of code is separated with a meaningful name, and we can see what the sketch is going to do at a glance.

First it will check the balance, then it will check the colour, and then it will print the colour to the serial port so we can see the values that it read.

Let`s explore the first private function, checkBalance, and add it to our code. Type the following below your loop function.

```
void checkBalance()
{
  //check if the balance has been set, if not, set it
  if(balanceSet == false){
	setBalance();
  }
}
 ```
 As you can see, if the balanceSet value (a boolean value) is set to false, then it makes a call to a secondary function called setBalance, where we set the white and black balancing readings. This will only happen when you boot up the arduino the one time.
 

```
void setBalance()
{
  //set white balance
   delay(5000);                          
//delay for five seconds, this gives us time to get a white sample in front of our sensor
  //scan the white sample.
  //go through each light, get a reading, set the base reading for each colour red, green, and blue to the white array
  for(int i = 0;i<=2;i++){
 	digitalWrite(ledArray[i],HIGH);
 	delay(100);
 	getReading(5);      	//number is the number of scans to take for average, this whole function is redundant, one reading works just as well.
 	whiteArray[i] = avgRead;
 	digitalWrite(ledArray[i],LOW);
 	delay(100);
  }
  //done scanning white, now it will pulse blue to tell you that it is time for the black (or grey) sample.
   //set black balance
    delay(5000);          	//wait for five seconds so we can position our black sample 
  //go ahead and scan, sets the colour values for red, green, and blue when exposed to black
  for(int i = 0;i<=2;i++){
 	digitalWrite(ledArray[i],HIGH);
 	delay(100);
 	getReading(5);
 	blackArray[i] = avgRead;
 	//blackArray[i] = analogRead(2);
 	digitalWrite(ledArray[i],LOW);
 	delay(100);
  }
   //set boolean value so we know that balance is set
  balanceSet = true;
  delay(5000);     //delay another 5 seconds to let us catch up
  }
 
```
If you noticed, we made yet another call to a function getReading.  We will add that right after we put in the checkColour function.

Once our balancing numbers have been set, we go on to finally read the colour. The function is basically the same as setBalance,, with the addition of the math that balances the reading. Let’s add it now.
```
void checkColour()
{
	for(int i = 0;i<=2;i++){
 	digitalWrite(ledArray[i],HIGH);  //turn or the LED, red, green or blue depending which iteration
 	delay(100);                  	//delay to allow CdS to stabalize, they are slow
 	getReading(5);              	//take a reading however many times
 	colourArray[i] = avgRead;    	//set the current colour in the array to the average reading
 	float greyDiff = whiteArray[i] - blackArray[i];                	//the highest possible return minus the lowest returns the area for values in between
 	colourArray[i] = (colourArray[i] - blackArray[i])/(greyDiff)*255; //the reading returned minus the lowest value divided by the possible range multiplied by 255 will give us a value roughly between 0-255 representing the value for the current reflectivity(for the colour it is exposed to) of what is being scanned
 	digitalWrite(ledArray[i],LOW);   //turn off the current LED
 	delay(100);
  }
 
 
}

```
We will also need to add our function getReading, otherwise our sketch won`t have real values. This function just allows us to take a few readings and average them out. This allows for a slightly smoother reading.

```
void getReading(int times){
  int reading;
  int tally=0;
  //take the reading however many times was requested and add them up

for(int i = 0;i < times;i++)
{
   reading = analogRead(0);
   tally = reading + tally;
   delay(10);
}
//calculate the average and set it
avgRead = (tally)/times;
}
```
Now we have a colour read into our colour holding array, all we need to do now is output it to the screen. Remember that we setup serial communication back in the setup function, all we have to do now is use the serial port to send out our data. The Arduino environment includes a serial monitor, which will allow you to see the data as it is passed from the Arduino. So let`s add the last function to the sketch.

```
//prints the colour in the colour array, in the next step, we will send this to processing to see how good the sensor works.
void printColour(){
Serial.print("R = ");
Serial.println(int(colourArray[0]));
Serial.print("G = ");
Serial.println(int(colourArray[1]));
Serial.print("B = ");
Serial.println(int(colourArray[2]));
//delay(2000);
}

```
 
This will print out some data that looks something like this
 
R = 231

G = 71

B = 0
 
which would be the equivilent to a red-orange colour.
 







