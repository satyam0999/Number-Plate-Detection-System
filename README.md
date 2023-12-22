# Number-Plate-Detection-System

# Number Plate Detection System

The Number Plate Detection System is a computer vision project that uses TensorFlow's Object Detection API to identify and localize license plates in images. This system can be useful for applications such as automated toll collection, parking management, and traffic monitoring.

## Table of Contents
1. [Overview](#overview)
2. [Setup](#setup)
   - [Setup Paths](#1-setup-paths)
   - [Download TF Models Pretrained Models and Install TFOD](#2-download-tf-models-pretrained-models-and-install-tfod)
3. [Data Preparation](#data-preparation)
   - [Create Label Map](#3-create-label-map)
   - [Create TF Records](#4-create-tf-records)
4. [Model Configuration](#model-configuration)
   - [Copy Model Config to Training Folder](#5-copy-model-config-to-training-folder)
   - [Update Config For Transfer Learning](#6-update-config-for-transfer-learning)
5. [Training](#training)
   - [Train the Model](#7-train-the-model)
6. [Evaluation](#evaluation)
   - [Evaluate the Model](#8-evaluate-the-model)
7. [Inference](#inference)
   - [Load Train Model From Checkpoint](#9-load-train-model-from-checkpoint)
   - [Detect from an Image](#10-detect-from-an-image)


## Overview

The goal of this project is to provide a robust and accurate system for detecting license plates in images. The system is built on TensorFlow's Object Detection API and includes scripts for setting up the environment, downloading pre-trained models, preparing the data, configuring the model, training, evaluating, and using the trained model for inference.

## Setup

### 1. Setup Paths
Ensure necessary paths are set up for the project by running the provided script. This script creates directories for workspace, scripts, annotations, images, models, and more.

```bash
python setup_paths.py
```


### 2. Download TF Models Pretrained Models and Install TFOD
Download the TensorFlow Models pretrained models from the TensorFlow Model Zoo and install the TensorFlow Object Detection (TFOD) API.

```bash
python setup_tfod.py
```

### 3. Create Label Map
Define the labels for the detection classes (e.g., license plates) and create a label map file.

```bash
python create_label_map.py
```

### 4. Create TF Records
Generate TF records from the provided images for training and testing the model.

```bash
python generate_tfrecord.py -x Tensorflow/workspace/images/train -l Tensorflow/workspace/annotations/label_map.pbtxt -o Tensorflow/workspace/annotations/train.record
python generate_tfrecord.py -x Tensorflow/workspace/images/test -l Tensorflow/workspace/annotations/label_map.pbtxt -o Tensorflow/workspace/annotations/test.record
```

### 5. Copy Model Config to Training Folder
Copy the pretrained model configuration file to the training folder.

```bash
python copy_model_config.py
```

### 6. Update Config For Transfer Learning
Adjust the model configuration for transfer learning by updating the pipeline configuration file.

```bash
python update_config_for_transfer_learning.py
```

### 7. Train the Model
Train the model using the specified configuration and pipeline.

```bash
python train_model.py
```
### 8. Evaluate the Model
Evaluate the trained model using the evaluation script.

```bash
python evaluate_model.py
```

### 9. Load Train Model From Checkpoint
Load the trained model from the checkpoint for inference.

```bash
python load_model_from_checkpoint.py
```

### 10. Detect from an Image
Use the trained model to detect license plates in an image.

```bash
python detect_from_image.py
```




