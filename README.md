# Semi-automated-Parking-Lot-Detection
This project uses YOLOv5 and VGG16 for parking space detection. The idea is to first visually locate the positions of all vehicles, then use their coordinates to crop and test with the VGG16 CNN model.

For this project, a few assupmtions must be made:
a. This project is applicable to all parking lots, not restricted by parking lot with lines.
b. The first detection assumes that the parking lot is full.

To replicate this project:
1. Develop the model from https://github.com/jowellhong/VGG16-Parking-Detection.git
2. Recreate the YOLOv5 vehicle detection model developed by Maryam Boneh: https://github.com/MaryamBoneh/Vehicle-Detection.git 
3. The weight of the training is in this github, exp16/weights/ folder: best.pt
4. Load main.ipynb to test with parkinglot2full.jpg (first detection with YOLOv5 to locate) and parkinglot2.jpeg (second detection to determine with VGG16 CNN model), modify necessary directories.
5. To run on realtime with camera, check the try_laptop_camera.ipynb

Jetson Nano Inference:
1. Install python virtual environment, avoid using 3rd party softwares on Jetson Nano to increase effieciency.
2. Install Juypyter Lab.
3. Load virtual environment, install necassary dependancies for TensorFlow and YOLOv5. Check YOLOv5 official github: https://github.com/ultralytics/yolov5.git
4. When installing dependencies, open yolov5/requirements.txt to check necassary libraries. YOLOv5 is only compatible with python 3.7 and above and Jetson Nano is equipped with python 3.6.9. Install manually according to the text, older version would affect the performance of the detection but it will work.
5. Load mainJN.ipynb to test with Jetson Nano.
6. Load camera_mainJN.ipynb to run detection on realtime with camera. To install camera on Jetson Nano, check: https://jetsonhacks.com/2019/04/02/jetson-nano-raspberry-pi-camera/

Jetson Nano Problem:
1. Due to compatibility issues, the GPU on Jetson Nano is not activating, affecting the results of the detection, sometimes it took too long to load.
2. Jetson Nano became too hot and force to shut down.
