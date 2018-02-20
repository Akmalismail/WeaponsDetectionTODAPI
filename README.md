# Weapons Detection in Surveillance Videos using Neural Networks

This repository is to replicate the evaluation results the results below. This project uses [Tensorflow Object Detection API](https://github.com/tensorflow/models/tree/master/research/object_detection) to build its neural network. This repository will not be maintained and will use versions as of 21/2/2018 all on Windows OS.

## Evaluation Results

| Model name | Class | AP (%) | mAP (%) |
| :---: | :---: | :---: | :---: |
| [ssd_mobilenet_v1_coco](http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17.tar.gz) | Gun<br>Knife<br>Grenade | 35.74<br>15.18<br>37.66 | 29.53 |
| [ssd_inception_v2_coco](http://download.tensorflow.org/models/object_detection/ssd_inception_v2_coco_2017_11_17.tar.gz) | Gun<br>Knife | 68.25<br>91.22 | 79.74 |
| [faster_rcnn_inception_v2_coco](http://download.tensorflow.org/models/object_detection/faster_rcnn_inception_v2_coco_2018_01_28.tar.gz) | Gun<br>Knife | 83.63<br>92.11 | 87.87 |
| [faster_rcnn_resnet101_coco](http://download.tensorflow.org/models/object_detection/faster_rcnn_resnet101_coco_2018_01_28.tar.gz) | Gun<br>Knife | 79.64<br>91.86 | 85.75 |


## Dependencies

All dependencies must be downloaded and installed. pip install can be used for most of these.
* This repo. (Clone or download, rename Folder WeaponsDetectionTODAPI-master to WeaponsDetectionTODAPI)
* All dependencies for the [API](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md)
* [Tensorflow](https://www.tensorflow.org/install/) (preferably with a GPU)


## Setting up the API

TODAPI uses Protobufs to configure model and training parameters. Run the command below to compile the protobuf libraries:


``` bash
# From WeaponsDetectionTODAPI
protoc-3.4.0-win32/bin/protoc models/research/object_detection/protos/*.proto --python_out=.
```


TODAPI needs both of the directories below added to PATH in environment variables:

``` bash
WeaponsDetectionTODAPI/models/research
WeaponsDetectionTODAPI/models/research/slim
```

