# YOLO docs
- use yolov11
https://docs.ultralytics.com/ the quickstart guide is really helpful just make a venv and install ultralytics
to view a webcam use --source 0
to train look in https://docs.ultralytics.com/modes/train/
to convert to a onix so that it can be converted to a hef

to train read the docs use
- I think that we will use roboflow to generate the training data
then we can export it in the yolov11 format

# convert to hef to run on the rasberry pi ai exelarator
https://github.com/hailo-ai/hailo_model_zoo -- used in the video below
https://github.com/LukeDitria/RasPi_YOLO -- the git that has useful scripts to get the data flow compiler to work
https://www.youtube.com/watch?v=Dm37x7sObIc -- a video guide that explains how to convert a yolov11 model to a hef
https://hailo.ai/developer-zone/documentation/hailo-sw-suite-2025-04/?sp_referrer=suite/suite_install.html -- the official documentation for the Hailo SW Suite

when you download the zip file from https://hailo.ai/developer-zone/software-downloads/
use the docker option
unzip it then then run the *.sh

also you can run """hailo tutorial""" this will pull up some jupyter notebooks that will give you a better understanding to convert your model to a hef:w
