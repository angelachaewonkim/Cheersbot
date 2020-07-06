# Cheersbot
Let's Cheers with Cheersbot!

### Watch the Demo video & Slide
[![Video Label](http://img.youtube.com/vi/7Yft4uTX8Ms/0.jpg)](https://youtu.be/7Yft4uTX8Ms=0s)

[Link to Slide](https://docs.google.com/presentation/d/1DhWW_3buYzDjDduUoTDXJvPRc6uU8FgfSCC8IZCqkdQ/edit?usp=sharing)

## introduction
After the Covid 19 Pandemic, people cannot drink outside. People are looking for alternatives such as 'Drinking with friends through video-call'. This new type of drinking culture is beginning to trend.
But-Dr. Priscilla Martinez, from Alcohol Research Group  says, "It is important to know your drinking status." The doctor said that to avoid side effects such as alcoholism, it is necessary to observe the changes in drinking time, reason, and amount of alcohol. 
Much have changed a lot from our daily lives, and the interaction between people is limited. It is getting too long to say that you have to be patient during this period.
Our team thought that enjoying time wisely with fun interaction is what people need.

We focus on the problem that drinking through video call can fills visual and auditory elements, but not physical interaction. Also, since you are drinking alone, it is important to know your drinking status.

## Pre-requirement
### Files needed for audio output & Voice recognition
#### How we get '.wav' file 
1. visit [NAVER CLOVA](https://clova.ai/voice)
2. you can record sentence with AI voice. record the sentence for '1zzan.mp3', '2zzan.mp3'and so on.
3. If you get .mp3 file, visit the [audio converter website](https://online-audio-converter.com/ko/) to convert .mp3 file to .wav file.
4. Open your file and click the wav button and '변환(convert)'button in order.

#### How we get '.pmdl' file
snowboy provides a personal model. The process is very simple, like this:

1. visit the [Snowboy website](https://snowboy.kitt.ai/)
2. Login in with social media
3. click the Create Hotword and set your Hotword like "how much glasses I drink?" and record your voice
4. Test the model and click save and download button. Then you can get pmdl (personal model) files

### Hardware Components
![cheersbot_component](https://user-images.githubusercontent.com/44702454/86465579-e38ce200-bd6c-11ea-936a-edb10434db80.png)
+ Jetbot
+ Speaker (for auditory interaction)
+ Glass (for physical interaction)
+ IMU Sensor (for collecting accelerometer data)
+ Medium-density fibreboard(MDF) (for Laser-cutted customized appearance)

### Software setup
### How to download trianed model
you need to download COCO-trained models
To detect the hand with various types of glass, we used pre-trained neural network pre-trained on the COCO dataset.
COCO-dataset is specialized in large-scaled object detection. 

It includes:
+ index 0- Person
+ index 47- Cup
+ If a hand with glass is in front of camera, then this model can detect it as index 0 or 47.
You can download the pre-trained engine in [here](https://drive.google.com/file/d/1eZsGracgHo5zSakGMHcW2ET19UtLfDKf/view?usp=sharing)

The model is made from the ObjectDetector API(from TensorFlow).
Once the model is built, NVIDIA TensorRT can optimize it: real-time execution is capable on Jetson Nano.
Using this model, we don't have to train and optimize the model.

#### Installation
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

```
pip3 install FaBo9Axis_MPU9250
```

Refer to the following [link](https://brisbaneroboticsclub.id.au/install-keystudio-i2c-shield-v1/)

2. Install the snowboy and make your own pmdl model
You can do it in following [Snowboy website](https://snowboy.kitt.ai/) 
(You have to register and make your own id)

We made two models: howmuch.pmdl(using 'How much cheers?') and zzanhalgga(using 'Shall we cheers?')
Download the pmdl model and store them in the path which contains your python notebook.

#### Download
1. Download the wav files and store them at the path which contains your notebook.
You can download them in [here](https://drive.google.com/drive/folders/1hhn2-ccdgHKmKi6KiMCy6lB9r9NzFBiP?usp=sharing)

2. Download the 'ssd_mobilenet_v2_coco.engine' dataset(You can easily find it in Google) and store it at the path which contains your notebook.

## How to operate
1. Except last two cells, all of the cells above import the required modules and define the function.
2. If you run a cell containing a while loop, 
	1. If your hand and glass is in front of the Cheersbot, it detects your hand with glass and moves forward.
	2. If you do 'Cheers' interaction with it, it moves backward
	3. After that, say specific sentence(such as 'Shall we cheers?' or 'How much cheers?') then it will give the auditory feedbacks.
	4. Iterate it until the while loop is terminated.
	5. If Cheersbot doesn't stop, excute last cell.
## Overall Flowchart
![image](https://user-images.githubusercontent.com/44702454/86480632-55732480-bd89-11ea-98f5-0b8ee45d7015.png)
### Four Main feature
1. 'Cheers' Interaction
2. Voice Recognition & Feedback
3. Let me know how much I drink
4. Reject cheers if the user drinkd too much


<img src = "https://user-images.githubusercontent.com/44702454/86477443-69b42300-bd83-11ea-9d7e-5a8479e8b8e1.png" width="500px"><img src = "https://user-images.githubusercontent.com/44702454/86477490-7fc1e380-bd83-11ea-9535-67d6fa3e4c94.png" width="500px">
<img src = "https://user-images.githubusercontent.com/44702454/86477516-8a7c7880-bd83-11ea-8984-2866039661e9.png" width="500px"><img src = "https://user-images.githubusercontent.com/44702454/86477533-9405e080-bd83-11ea-8440-4bd8b2112f6d.png" width="500px">
<img src = "https://user-images.githubusercontent.com/44702454/86477550-9f590c00-bd83-11ea-8136-dc7f1abef642.png" width="500px"><img src = "https://user-images.githubusercontent.com/44702454/86477566-a849dd80-bd83-11ea-99ce-cbcc2f99d640.png" width="500px">

![mainfeature3](https://user-images.githubusercontent.com/44702454/86477550-9f590c00-bd83-11ea-8136-dc7f1abef642.png)
![mainfeature4](https://user-images.githubusercontent.com/44702454/86477566-a849dd80-bd83-11ea-99ce-cbcc2f99d640.png)

## Laser-cutted customized appearance
I use my school's free laser cutting area('IDEA FACTORY' @KAIST) so, This tutorial is totally dependent on certain place's condition. In my case,'.DXF file' is needed, if you trying to use laser cutting machine @ IDEA FACTORY.
![KakaoTalk_20200703_234655791_13](https://user-images.githubusercontent.com/44702454/86485100-cff47200-bd92-11ea-998d-e77e128b2677.jpg)

There were lot of ways to make .DXF file. If you are not good at manipulating tool such as AutoCAD,Fusion360 from Autodesk.
I recommend very usefull [website.](https://en.makercase.com/#/) This welsite provide basic model as .DXF file. still, it needs a little modification, but You can make .DXF file easier.
I expecially consider that Jetbot should attached with lots of lines. so that I made a hole for lines.
(I attached `Cheersbot(ProductDrawing).dxf` file)
once, you make .DXF file bring it to laser cutting machine.and Then, run the machine.

Then, you will get a seperate MDF part. Glue the parts with super glue. 


