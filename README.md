# YOLOv8 Object Detection with Angle Prediction

This repository contains code and resources for training and deploying a YOLOv8 model for object detection with angle prediction. The project extends the YOLOv8 model to predict not only bounding boxes but also the orientation angles of objects in images.

## Table of Contents

- [Overview](#overview)
- [Dataset Preparation](#dataset-preparation)
- [Installation](#installation)
- [Training](#training)
- [Inference](#inference)
- [Evaluation](#evaluation)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project is an extension of the YOLOv8 model, focusing on detecting objects and predicting their orientation angles. The model can be used in various applications such as robotics, computer vision, and autonomous driving.

Key features:
- Predicts bounding boxes and angles for objects in images.
- Supports the YOLOv8 model with modifications for angle prediction.
- Includes training, validation, and testing scripts.

## Dataset Preparation

The dataset used for training the model includes images with annotated bounding boxes and angles. The dataset is structured as follows:
- **train/**: Training images and annotations
- **test/**: Testing images and annotations
- **validate/**: Validation images and annotations

Ensure the dataset is in the YOLOv8 format, with the following files:
- Annotations in the `train/`, `test/`, and `validate/` folders
- A `README.md` file with a dataset description
- A `data.yaml` file containing the class labels and paths

## Training

To train the YOLOv8 model with angle prediction:

1. **Modify the configuration**:
   Edit the `config.yaml` file to set up your dataset paths and hyperparameters.

2. **Run the training script**:
   ```bash
   python train.py --data data.yaml --cfg config.yaml --weights yolov8.pt --epochs 100
   ```

## Inference

To run inference on new images using the trained model:

```bash
python detect.py --source your_image.jpg --weights best.pt --conf 0.25 --save-txt --save-conf --agnostic-nms
```

This will output the detected objects along with their bounding boxes and predicted angles.

## Evaluation

Evaluate the model performance using the test set:

```bash
python val.py --data data.yaml --weights best.pt --task test --save-json
```

The evaluation metrics include Mean Average Precision (mAP), Angle Error, and more.

## Results

Include the results of the training and evaluation, such as:
- Training and validation loss curves
- Sample predictions with bounding boxes and angles
- Performance metrics

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request. You can also report any issues or suggest enhancements via the issue tracker.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
