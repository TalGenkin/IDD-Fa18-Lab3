# Data Logger - Lab 3

*A lab report by Tal Genkin.*


## Part A.  Writing to the Serial Monitor
 
**a. Based on the readings from the serial monitor, what is the range of the analog values being read?**

The range is between around 670 to around 730
 
**b. How many bits of resolution does the analog to digital converter (ADC) on the Arduino have?**

According to the range of values, it seem the Arduino is using 10 bits (since the range of values is between 512 and 1024)

## Part B. RGB LED

**How might you use this with only the parts in your kit? Show us your solution.**

[RGB LED](https://youtu.be/Ys_Ekg8ndvE)

## Part C. Voltage Varying Sensors 
 
### 1. FSR, Flex Sensor, Photo cell, Softpot

**a. What voltage values do you see from your force sensor?**

The voltage changes in the values of around 720V to almost 800V. 

[FSR](https://youtu.be/nyNDtQdpX3g)

**b. What kind of relationship does the voltage have as a function of the force applied? (e.g., linear?)**

The relationship looks like a Log / Ln function in the change in value of volts. 

**c. Can you change the LED fading code values so that you get the full range of output voltages from the LED when using your FSR?**

I need to change the maximum brightness (to 1023)

[LED Fading](https://www.youtube.com/watch?v=8kaDEiu9KCs&feature=youtu.be)

[LED Fading 2](https://youtu.be/fZZJy8SGqw0)

**d. What resistance do you need to have in series to get a reasonable range of voltages from each sensor?**

[Felx sensor](https://youtu.be/xwesb1x9bPU)

For the flex sensor I used a resistor of 27K Ohm, with which I got voltage values of 150V - 550V approx.

Without resistance - the voltage is 1023, with a 22k resistor, the votage is around 300. With a 5k resistor the voltage is 126V.

With the Photo cell, with a 27k resistance, the voltage values are between 830 and 960. 
With a 22k resistance, the values are between 800 and 930.
With a 5k resistance, the values are between 500 and 760

With the Soft pot, the values range between around 700V (although for a millisecond it goes to 0, if the reading is correct) up to 1023.

**e. What kind of relationship does the resistance have as a function of stimulus? (e.g., linear?)**

The relationship is not linear, as we can see that, with the Photo cell for example, with a chenge in 4k ohm of resistance, it change the values in about 30V, about with another 17K Ohm (4 times as much) change in resistance, it changes the values in about 300V (10 times as much).

### 2. Accelerometer
 
**a. Include your accelerometer read-out code in your write-up.**

// Used for software SPI
#define LIS3DH_CLK 13
#define LIS3DH_MISO 12
#define LIS3DH_MOSI 11
// Used for hardware & software SPI
#define LIS3DH_CS 10

// software SPI
//Adafruit_LIS3DH lis = Adafruit_LIS3DH(LIS3DH_CS, LIS3DH_MOSI, LIS3DH_MISO, LIS3DH_CLK);
// hardware SPI
//Adafruit_LIS3DH lis = Adafruit_LIS3DH(LIS3DH_CS);
// I2C
Adafruit_LIS3DH lis = Adafruit_LIS3DH();

### 3. IR Proximity Sensor

**a. Describe the voltage change over the sensing range of the sensor. A sketch of voltage vs. distance would work also. Does it match up with what you expect from the datasheet?**

[Proximity sensor tested](https://youtu.be/LUwZHogVOM0)

**b. Upload your merged code to your lab report repository and link to it here.**

[Code from Arduino](acceldemo.ino)

## Optional. Graphic Display

**Take a picture of your screen working insert it here!**

![Screen working with Proximity sensor](ProximityTest.JPG)

## Part D. Logging values to the EEPROM and reading them back
 
### 1. Reading and writing values to the Arduino EEPROM

**a. Does it matter what actions are assigned to which state? Why?**

**b. Why is the code here all in the setup() functions and not in the loop() functions?**

**c. How many byte-sized data samples can you store on the Atmega328?**

**d. How would you get analog data from the Arduino analog pins to be byte-sized? How about analog data from the I2C devices?**

**e. Alternately, how would we store the data if it were bigger than a byte? (hint: take a look at the [EEPROMPut](https://www.arduino.cc/en/Reference/EEPROMPut) example)**

**Upload your modified code that takes in analog values from your sensors and prints them back out to the Arduino Serial Monitor.**

### 2. Design your logger
 
**a. Insert here a copy of your final state diagram.**

### 3. Create your data logger!
 
**a. Record and upload a short demo video of your logger in action.**
