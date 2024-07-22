# YOLOv10 TensorRT Project

## Overview

The YOLOv10 TensorRT Project provides an efficient way to perform object detection using the YOLOv10 model with NVIDIA TensorRT for optimized inference. This project supports running inference on videos and images and converting ONNX models to TensorRT engine files.

## Table of Contents

- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage)
  - [Convert ONNX Model to TensorRT Engine](#convert-onnx-model-to-tensorrt-engine)
  - [Run Inference on Video](#run-inference-on-video)
  - [Run Inference on Image](#run-inference-on-image)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Project Structure
YOLOv10-TensorRT/

│── include/

│ ├── YOLOv10.hpp

│── src/

│ ├── main.cpp

│ ├── YOLOv10.cpp

│── CMakeLists.txt

└── README.md
## Dependencies

- **OpenCV**: For image and video processing.
- **CUDA**: For GPU acceleration.
- **TensorRT**: For optimized inference with YOLOv10.
- **ONNX Runtime**: For model conversion.

## Installation

### 1. Install Dependencies

- **OpenCV**: Follow the instructions on the [OpenCV official website](https://opencv.org/) to install OpenCV.
- **CUDA**: Install CUDA from the [NVIDIA website](https://developer.nvidia.com/cuda-toolkit).
- **TensorRT**: Download and install TensorRT from the [NVIDIA Developer website](https://developer.nvidia.com/tensorrt).
- **ONNX Runtime**: Install ONNX Runtime from [ONNX Runtime GitHub](https://github.com/microsoft/onnxruntime).

### 2. Clone the Repository


git clone [https://github.com/yourusername/YOLOv10-TensorRT.git](https://github.com/hamdiboukamcha/yolov10-tensorrt.git)
cd yolov10-tensorrt/Yolov10-TensorRT

mkdir build
cd build
cmake ..
cmake --build .
## Usage

### Convert ONNX Model to TensorRT Engine

To convert an ONNX model to a TensorRT engine file, use the following command:

./YOLOv10Project convert path_to_your_model.onnx path_to_your_engine.engine

path_to_your_model.onnx: Path to the ONNX model file.
path_to_your_engine.engine: Path where the TensorRT engine file will be saved.

### Run Inference on Video
To run inference on a video, use the following command:
./YOLOv10Project infer_video path_to_your_video.mp4 path_to_your_engine.engine

path_to_your_video.mp4: Path to the input video file.
path_to_your_engine.engine: Path to the TensorRT engine file.

### Run Inference on Video
Run Inference on Image
To run inference on an image, use the following command:
./YOLOv10Project infer_image path_to_your_image.jpg path_to_your_engine.engine
path_to_your_image.jpg: Path to the input image file.
path_to_your_engine.engine: Path to the TensorRT engine file.

## Configuration

### CMake Configuration
In the CMakeLists.txt, update the paths for TensorRT and OpenCV if they are installed in non-default locations:

#### Set the path to TensorRT installation
set(TENSORRT_PATH "path/to/TensorRT")  # Update this to the actual path
Ensure that the path points to the directory where TensorRT is installed.

### Troubleshooting
Cannot find nvinfer.lib: Ensure that TensorRT is correctly installed and that nvinfer.lib is in the specified path. Update CMakeLists.txt to include the correct path to TensorRT libraries.

Linker Errors: Verify that all dependencies (OpenCV, CUDA, TensorRT) are correctly installed and that their paths are correctly set in CMakeLists.txt.

Run-time Errors: Ensure that your system has the correct CUDA drivers and that TensorRT runtime libraries are accessible. Add TensorRT’s bin directory to your system PATH.


