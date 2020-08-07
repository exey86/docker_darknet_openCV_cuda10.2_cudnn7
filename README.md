# docker_darknet_openCV_cuda10.2_cudnn7
YOLOv4 on Ubuntu 18.04 with OpenCV, CUDA 10.2 and cuDNN 7

This file will pull from dockerhub an image with Ubuntu 18.04 + CUDA 10.2 + cuDNN 7, will compile OpenCV and YOLOv4.

Requirements
* Linux
* Nvidia drivers installed
* Nvidia Container Toolkit (https://github.com/NVIDIA/nvidia-docker)

How to use
1) First, download the dockerfile and build the image (it will take a while, take a coffee :)):

		docker build -t imageName .
2) Second, run the image:


		docker run -it --gpus all --net host -e DISPLAY=$DISPLAY -v $HOME/.Xauthority:/root/.Xauthority imageName

3) Now you are able to use Yolo v4, for example:


		./darknet detector test ./cfg/coco.data ./cfg/yolov4.cfg ./yolov4.weights data/dog.jpg
	
