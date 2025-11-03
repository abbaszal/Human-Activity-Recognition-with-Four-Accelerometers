# Activity Recognition with Four Accelerometers

This repository contains the report **"Activity Recognition with Four Accelerometers"** . 

The study leverages wearable accelerometer data to recognize physical activities through deep learning. 

Two primary models are evaluated: a pure Convolutional Neural Network (CNN) and a hybrid CNN with Gated Recurrent Units (CNN-GRU).




## Overview

In modern health research, wearable sensors enable continuous, objective tracking of physical activities. In this project, 32 healthy adults wore four accelerometers (left wrist, left hip, left ankle, and right ankle) while engaging in activities such as walking and stair climbing. The collected high-frequency data is preprocessed and segmented into windows before being fed into two deep learning models:

- **CNN Model:** Extracts spatial features from the raw accelerometer data.
- **CNN-GRU Model:** Enhances feature extraction by incorporating temporal dynamics through GRU layers.

The main objective is to improve activity classification accuracy by exploring different data preprocessing strategies and sensor combinations.

---

## Repository Contents

- **Rostami_Zal_Activity_Recognition_with_Four_Accelerometers.pdf**  
  The complete report detailing methodology, experiments, and analysis.
- **Notebooks**  
  Contains notebooks used to train models, and generate results.

---

## Project Description

### Data and Preprocessing

The dataset consists of raw accelerometer signals recorded at 100Hz. Key preprocessing steps include:

- **Data Combination:**  
  Merging CSV files from 32 participants to form a comprehensive dataset (≈2 million rows).

- **Windowing:**  
  Segmenting data into fixed-size windows (256, 512, or 1024 samples) with corresponding step sizes. Two preprocessing approaches are used:
  - **Preprocessing-1:** Direct segmentation with noise reduction and normalization.
  - **Preprocessing-2:** Windowing followed by the extraction of statistical and frequency-domain features (e.g., FFT and DCT).

- **Noise Reduction & Normalization:**  
  Removal of baseline wander via median filters and normalization using percentile-based methods or Median Absolute Deviation (MAD).

### Model Architectures

- **CNN Model:**  
  Composed of several 1D convolutional layers (with increasing filter sizes), batch normalization, max pooling, and dropout, followed by fully connected layers ending with a softmax output layer for three activity classes.

- **CNN-GRU Model:**  
  Combines initial CNN layers for spatial feature extraction with one or two GRU layers (128 units each) to capture temporal dependencies. The architecture concludes with dense layers and a softmax output for classification.

---

## Detailed Results

The evaluation of the models focused on key metrics: accuracy, precision, recall, and F1 score. Below are the summarized findings from multiple experimental setups.

### CNN Model – Preprocessing-1 (Single Signal Selection)

| Window Size (Step Size) | Joint        | Accuracy (%) |
|--------------------------|--------------|---------------|
| **256 (256)**            | Left Wrist   | 87.4          |
|                          | Left Hip     | 97.6          |
|                          | Left Ankle   | 97.3          |
|                          | Right Ankle  | 99.0          |
| **512 (512)**            | Left Wrist   | 85.6          |
|                          | Left Hip     | 95.8          |
|                          | Left Ankle   | 98.9          |
|                          | Right Ankle  | 99.6          |
| **1024 (256)**           | Left Wrist   | 87.4          |
|                          | Left Hip     | 98.5          |
|                          | Left Ankle   | 99.6          |
|                          | Right Ankle  | 99.6          |


*Observation:* When using individual sensor data, the models consistently performed best with hip and ankle sensors. The wrist sensor, while slightly lower, still provided robust performance.

### CNN Model – Preprocessing-1 (Combined Sensor Data)

- **Combined Data (Window Size 256):**  
  Achieved a weighted average F1 score of **0.95**.
  
*Observation:* Combining data from all four sensors enhanced classification performance by leveraging complementary information from multiple sensor placements.

### CNN Model – Preprocessing-2 (Feature Extraction Approach)

| Window Size | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |
|--------------|---------------|----------------|-------------|---------------|
| **256**      | 98            | 95             | 95          | 95            |
| **512**      | 99            | 99             | 97          | 98            |
| **1024**     | 98            | 97             | 91          | 94            |


*Observation:* The second preprocessing approach (with feature extraction) yielded high performance, particularly at a window size of 512 samples, showing a slight trade-off between recall and precision at larger window sizes.

### CNN-GRU Model Results

**Performance across different window sizes and step sizes:**

| Window Size (Step Size) | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |
|--------------------------|---------------|----------------|-------------|---------------|
| **256 (256)**            | 98            | 98             | 98          | 98            |
| **512 (512)**            | 98            | 98             | 98          | 98            |
| **1024 (256)**           | 98            | 99             | 98          | 98            |


*Observation:* The CNN-GRU model exhibited consistent performance across different settings, indicating the robustness of combining convolutional feature extraction with temporal sequence modeling.

### Comparative Insights

- **Sensor Placement:**  
  Sensors on the hip and ankles deliver the most reliable signals, whereas wrist sensor data is slightly less effective.
- **Multi-Sensor Fusion:**  
  Integrating data from all sensor locations generally leads to improved accuracy and robustness.
- **Model Robustness:**  
  Both the CNN and CNN-GRU models outperform traditional methods (such as Classification Trees), with the CNN-GRU model offering a marginally more stable performance across various window sizes.

For further details and additional performance tables, please refer to the full report.

---

## Future Work

- **Sensor Placement Optimization:**  
  Investigate optimal sensor configurations to further enhance classification accuracy.
- **Expanding Sensor Modalities:**  
  Explore the integration of additional sensor types to capture more complex or subtle activities.
- **Enhanced Feature Engineering:**  
  Delve into advanced feature extraction methods to improve model robustness.
- **Real-World Deployment:**  
  Validate the models in real-life settings beyond controlled experiments.

---

## References

Key literature includes:
- Studies on deep learning architectures (CNNs, GRUs) for time series and accelerometry data.
- Research on signal processing techniques such as baseline removal and normalization.
- Comparative analysis with traditional classification methods.

For complete references, please consult the PDF report.

---

## Contact

For questions or collaboration, please contact:
- **Amirhossein Rostami:** [amirhossein.rostami@studenti.unipd.it](mailto:amirhossein.rostami@studenti.unipd.it)
- **Abbas Zal:** [abbas.zal@studenti.unipd.it](mailto:abbas.zal@studenti.unipd.it)


---
