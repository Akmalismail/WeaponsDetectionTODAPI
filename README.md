# Weapons Detection in Surveillance Videos using Neural Networks

This repository is to replicate the evaluation results the results below. This project uses [Tensorflow Object Detection API] (https://github.com/tensorflow/models/tree/master/research/object_detection) to build its neural network. This repository will not be maintained and will use versions as of 21/2/2018 all on Windows OS.


## Dependencies

All dependencies must be downloaded and installed. pip install can be used for most of these.
* This repo. (Clone or download)
* All dependencies for the [API] (https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md)
* [Tensorflow] (https://www.tensorflow.org/install/) (preferably with a GPU)


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

