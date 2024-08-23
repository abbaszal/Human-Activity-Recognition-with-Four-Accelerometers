
# Activity Recognition Using Accelerometer Data

## Project Overview

This project focuses on the use of wearable accelerometers for activity recognition. By leveraging data from multiple accelerometers placed on different parts of the body, we aim to accurately classify physical activities such as walking, ascending stairs, and descending stairs. The project employs advanced machine learning techniques, including Convolutional Neural Networks (CNN) and a combination of CNN with Gated Recurrent Unit (GRU) models, to enhance the accuracy of activity recognition.

### Team Members
- **Amirhossein Rostami** 
- **Abbas Zal** 

## Problem and Approach

### Introduction

Wearable accelerometers have become integral in health research due to their ability to provide precise, continuous measurements of physical activity. Our primary objective is to utilize accelerometer data to improve activity recognition through sophisticated modeling approaches.

### Methods Used

- **Convolutional Neural Networks (CNN)**
- **Combination of CNN and GRU units**
- **Data Preprocessing Techniques**: Baseline Wander Removal, Normalization, and Feature Extraction.

## Data Preprocessing

### Structure of Data

The dataset consists of measurements from four accelerometers worn on the left wrist, left hip, left ankle, and right ankle. The columns in the dataset include:

- **Activity**: Type of activity performed.
- **Time (s)**: Time from device initiation in seconds.
- **Gravitational Measurements**: 
  - `lw_x, lw_y, lw_z`: Left wrist x, y, and z-axis.
  - `lh_x, lh_y, lh_z`: Left hip x, y, and z-axis.
  - `la_x, la_y, la_z`: Left ankle x, y, and z-axis.
  - `ra_x, ra_y, ra_z`: Right ankle x, y, and z-axis.

### Preprocessing Steps

1. **Signal Selection and Combination**:
   - Single signal selection or combination of all four signals.
   - Window selection approach with specific window size and step size.

2. **Feature Extraction**:
   - Extraction of normal and DCT/FFT features.
   - Normalization using Median Absolute Deviation (MAD).

3. **Activity Detection**:
   - Focus on three activities: walking, ascending stairs, and descending stairs.

## Model Architectures

### 1. CNN for Multivariate Time Series

The CNN model is composed of multiple layers designed to extract features from the accelerometer data and classify physical activities. The model has the following parameters:

- **Total parameters**: 1,440,131
- **Trainable parameters**: 1,438,211
- **Non-trainable parameters**: 1,920

### 2. CNN and GRU Model

The CNN-GRU model combines the strengths of CNN for feature extraction and GRU for sequential data processing, achieving better performance in activity recognition tasks. The model parameters are:

- **Total parameters**: 232,131
- **Trainable parameters**: 232,131
- **Non-trainable parameters**: 0

## Results

### CNN Model Performance

The CNN model was evaluated using different preprocessing methods, including single signal selection and combination of all four signals. The model's performance was assessed based on window size and step size parameters, with the following results:

- **Metrics**: Recall, Precision, F1 Score.


### CNN and GRU Model Performance

The CNN-GRU model was tested with various window and step sizes, producing strong results across all configurations.

## Conclusion

The project successfully demonstrated the effectiveness of accelerometer data in recognizing physical activities. Our results indicate that sensors placed on the ankles and hips provided the most reliable data, significantly outperforming wrist sensors. The combination of sophisticated data preprocessing techniques, deep neural networks, and ample input data contributed to the high performance of our models.
