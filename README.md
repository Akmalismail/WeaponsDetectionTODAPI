# Weapons Detection in Surveillance Videos using Neural Networks

This repository is to replicate the evaluation results the results below. This project uses [Tensorflow Object Detection API](https://github.com/tensorflow/models/tree/master/research/object_detection#tensorflow-object-detection-api) to build its neural network. This repository will not be maintained and will use versions as of 21/2/2018 all on Windows OS.


## Evaluation Results


<center>
| Model name | Class | AP (%) | mAP (%) |
| :--- | :---: | :---: | :---: |
| [SSD_MobileNet](http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17.tar.gz) | Gun<br>Knife<br>Grenade | 35.74<br>15.18<br>37.66 | 29.53 |
| [SSD_Inception](http://download.tensorflow.org/models/object_detection/ssd_inception_v2_coco_2017_11_17.tar.gz) | Gun<br>Knife | 68.25<br>91.22 | 79.74 |
| [Frcnn_Inception](http://download.tensorflow.org/models/object_detection/faster_rcnn_inception_v2_coco_2018_01_28.tar.gz) | Gun<br>Knife | 83.63<br>92.11 | 87.87 |
| [Frcnn_Resnet](http://download.tensorflow.org/models/object_detection/faster_rcnn_resnet101_coco_2018_01_28.tar.gz) | Gun<br>Knife | 79.64<br>91.86 | 85.75 |
</center>


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


## Installing Tensorflow Object Detection API

``` bash
# From WeaponsDetectionTODAPI
python models/research/setup.py
```


## Evaluating using TODAPI

Run these to evaluate such models

``` bash
# SSD_MobileNet
python models/research/object_detection/eval.py ^
--logtostderr ^
--pipeline_config_path="weapons_detection_model_1/ssd_mobilenet_v1_coco_11_06_2017/ssd_mobilenet_v1_pets.config" ^
--checkpoint_dir="weapons_detection_model_1/training" ^
--eval_dir="weapons_detection_model_1/testing" ^
--run_once=True

# SSD_Inception
python models/research/object_detection/eval.py ^
--logtostderr ^
--pipeline_config_path="weapons_detection_model_2/ssd_inception_v2_coco_2017_11_17/ssd_inception_v2_coco.config" ^
--checkpoint_dir="weapons_detection_model_2/training" ^
--eval_dir="weapons_detection_model_2/testing" ^
--run_once=True

# Frcnn_Inception
python models/research/object_detection/eval.py ^
--logtostderr ^
--pipeline_config_path="weapons_detection_model_3/faster_rcnn_inception_v2_coco_2017_11_08/faster_rcnn_inception_v2_coco.config" ^
--checkpoint_dir="weapons_detection_model_3/training" ^
--eval_dir="weapons_detection_model_3/testing" ^
--run_once=True

# Frcnn_Resnet
python models/research/object_detection/eval.py ^
--logtostderr ^
--pipeline_config_path="weapons_detection_model_4/faster_rcnn_resnet101_coco_2017_11_08/faster_rcnn_resnet101_voc07.config" ^
--checkpoint_dir="weapons_detection_model_4/training" ^
--eval_dir="weapons_detection_model_4/testing" ^
--run_once=True