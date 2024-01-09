
# Circle Detection ML Challenge Report

## Overview
The Circle Detection ML Challenge involves developing a deep learning model capable of locating a circle and determining its radius in a noisy image. This document summarizes the approach, including data generation, model architecture, training process, and evaluation.

## Data Generation
A dataset of noisy images with circles of varying radii and positions was generated using the following process:

- **Circle Drawing**: The `draw_circle` function was used to draw circles with anti-aliased edges on a black background.
- **Noise Addition**: Gaussian noise was added to the images to simulate real-world scenarios where image quality may vary.
- **Normalization**: The images were normalized to ensure pixel values were within the range [0, 1].

### Sample Generated Images
Below are examples of the generated images used for training:
![Sample Generated Images](https://github.com/Maryam-1/Circle-Detection-ML-Challenge-/blob/main/Screenshot%202024-01-09%20at%2015.47.40.png)

## Model Architecture
A Convolutional Neural Network (CNN) was employed with the following layers:

- **Convolutional Layers**: Two convolutional layers with ReLU activation were used to extract features from the images.
- **Pooling Layers**: MaxPooling layers followed each convolutional layer to reduce the spatial dimensions of the feature maps.
- **Flatten Layer**: A flatten layer was used to convert the 2D feature maps into a 1D feature vector.
- **Dense Layers**: Two dense layers followed the flatten layer, with the final layer outputting three values corresponding to the circle's center (x, y), and radius.

## Training Process
The model was trained using the following approach:

- **Loss Function**: Mean Squared Error (MSE) was used to quantify the difference between predicted and actual circle parameters.
- **Optimizer**: The Adam optimizer was used with a learning rate of 0.001 for stochastic gradient descent.
- **Batch Size**: A batch size of 32 was chosen for training.
- **Epochs**: The model was trained for 20 epochs.

## Evaluation
- **Intersection Over Union (IOU)**: The IOU metric was used to assess the overlap between predicted and actual circles. An IOU of 0.5 or higher is typically considered a successful prediction.

## Results
The model achieved an IOU performance of approximately 0.33, indicating a moderate level of accuracy. The training process showed a steady decrease in loss, suggesting that the model was learning the task to some extent. However, the validation loss indicated potential overfitting, as it plateaued and fluctuated towards the later epochs.




