# detectstuf - the criminal detector

detectstuf is a program that can run while you are away from home, waiting until an uninvited guest shows up at your door to take a picture which you can later submit to the police

## The Algorithm

How it works - the algorithm is a modified imagenet program, made to take input from a video camera and detect objects in its view. The program specifically searches for clothing, like shirts, pants, glasses, hoods and masks. Once any of those items are found, the program will take its first picture, and will keep running after that. However, once something generally found on the face is found like glasses, hats or hoods the program will take its second picture. This is done so that in the worst case scenario you would at least have a picture of the person's general appearance, and at best you would also have their face

## Running this project

To run the project you will need a few things. Obviously you need the Jetson nano. The nano should have a camera attached to it. Due to the pain of installing libraries, this project only uses two:

jetson.inference, 
jetson.utils

First download inference from https://github.com/dusty-nv/jetson-inference.
Then cd into the inference folder and download utils https://github.com/dusty-nv/jetson-utils in it.

After that download detectstuf, put it into the jetson-inference folder and make sure the python file is inside its own folder.
Images of how it should look have been provided with the download.

Finally, to start the detection navigate to where you downloaded the project, and check that it is the right directory with the ls command. One of the files should be named detector.py

Once confirmed, run the command python3 detector.py v4l2:///dev/video0

The v4l2:///dev/video0 is the video device you have. 
Use https://github.com/dusty-nv/jetson-inference/blob/master/docs/aux-streaming.md to see if you need to change v4l2:///dev/video0 to something else.
If nothing works try simply running python3 detector.py

Once the camera turns on you know that its working. For best results have the camera face a blank wall. Bouth image files will be saved into the folder with the python file.

here is the video showing how to turn on and use detectstuf
https://youtu.be/BFagwODRP7E
