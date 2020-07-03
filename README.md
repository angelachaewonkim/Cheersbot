# Cheersbot
Cheers with Cheersbot!

### Watch the Demo video
[![Watch the video](https://i.imgur.com/vKb2F1B.png)](https://youtu.be/vt5fpE0bzSY)

## introduction
After the Covid 19 Pandemic, people cannot drink outside. People are looking for alternatives such as 'Drinking with friends through video-call'. This new type of drinking culture is beginning to trend.
But-Dr. Priscilla Martinez, from Alcohol Research Group  says, "It is important to know your drinking status." The doctor said that to avoid side effects such as alcoholism, it is necessary to observe the changes in drinking time, reason, and amount of alcohol. 
Much have changed a lot from our daily lives, and the interaction between people is limited. It is getting too long to say that you have to be patient during this period.
Our team thought that enjoying time wisely with fun interaction is what people need.

We focus on the problem that drinking through video call can fills visual and auditory elements, but not physical interaction. Also, since you are drinking alone, it is important to know your drinking status.

## Pre-requirement
### Hardware Components


### Software Components

## Installation
1. Please install smbus and FaBoAxis_MPU9250
In your terminal, make sure you have pip3 installled.

```python
sudo apt-get install python3-pip
```

Now clone the github site and install smbus2.

```python
sudo git clone https://github.com/FaBoPlatform/FaBo9AXIS-MPU9250-Python.git
pip3 install smbus2 <code>
```

Install the FaBo9Axis_MPU9250

`pip3 install FaBo9Axis_MPU9250`

Refer to the following link: https://brisbaneroboticsclub.id.au/install-keystudio-i2c-shield-v1/

2. Install the snowboy and make your own pmdl model
You can do it in following link: https://snowboy.kitt.ai/ 
(You have to register and make your own id)

We made two models: howmuch.pmdl(using 'How much cheers?') and zzanhalgga(using 'Shall we cheers?')
Download the pmdl model and store them in the path which contains your python notebook.

## Download
1. Download the wav files and store them at the path which contains your notebook.
You can download them in here: https://drive.google.com/drive/folders/1hhn2-ccdgHKmKi6KiMCy6lB9r9NzFBiP?usp=sharing

2. Download the 'ssd_mobilenet_v2_coco.engine' dataset(You can easily find it in Google.) and store it at the path which contains your notebook.

## How to operate
1. Except last two cells, all of the cells above import the required modules and define the function.
2. If you run a cell containing a while loop, 
	1. If your hand and glass is in front of the Cheersbot, it detects your hand with glass and moves forward.
	2. If you do 'Cheers' interaction with it, it moves backward
	3. After that, say specific sentence(such as 'Shall we cheers?' or 'How much cheers?') then it will give the auditory feedbacks.
	4. Iterate it until the while loop is terminated.
	5. If Cheersbot doesn't stop, excute last cell.


