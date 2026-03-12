[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/5HZkrI_Y)
[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/r8OAyKH-)

# CNN Classification Task with Cat-vs-Dog dataset

## Dataset

The dataset used for this task is **Dogs vs. Cats**:

[Kaggle Dataset - Dog vs. Cat](https://www.kaggle.com/datasets/shaunthesheep/microsoft-catsvsdogs-dataset/data)

### Dataset Details:

- **Content**: Images of dogs and cats.
- **Format**: JPEG images.
- **Labels**: 0 for cat, 1 for dog.

## Requirements

1. **Model Requirements**:
   - Build a CNN model.
   - Include at least:
     - Input layer for image data.
     - Multiple convolutional layers with appropriate activation functions.
     - Pooling layers (e.g., MaxPooling).
     - Fully connected layers leading to a softmax or sigmoid output.
   - Use **binary cross-entropy** as the loss function for binary classification.

2. **Evaluation**:
   - Use metrics such as **accuracy**, **precision**, **recall**, and **F1-score**.
   - Create visualizations for:
     - Model training and validation loss.
     - Model training and validation accuracy.
     - Confusion matrix.

3. **Documentation**:
   - Clearly document:
     - The architecture of the CNN model.
     - Evaluation results.

## Findings

Document your results and observations here:

- **Accuracy**: [0.91]
- **Loss**: [0.21 - 0.30]
- **Observations**:
  - CNN with **multiple convolution layers** achieved better feature extraction.
  - **Data augmentation** improved generalization and prevented overfitting.
  - **Dropout layer** helped stabilize training performance.
  - Training and validation curves showed stable learning behavior.
  - The model achieved balanced performance for both classes (cats and dogs).

# Documentation

## Data Preprocessing

Before training the CNN model, the dataset was preprocessed to ensure the images are suitable for training.

The following preprocessing steps were applied:

- Images were resized to **128 × 128 pixels**
- Pixel values were normalized using: **rescale = 1./255**

- Data augmentation techniques were applied to improve generalization and reduce overfitting:

Data augmentation included:

- Rotation
- Horizontal flipping
- Width shifting
- Height shifting
- Zooming

These techniques help the model learn robust features from the dataset.

---

# CNN Model Architecture

A Convolutional Neural Network (CNN) was implemented to perform the classification task.

The architecture includes the following layers:

### Input Layer

Input image size: **128 × 128 × 3**

### Convolution Block 1

- Conv2D (32 filters, 3×3 kernel)
- ReLU activation
- MaxPooling2D

### Convolution Block 2

- Conv2D (64 filters, 3×3 kernel)
- ReLU activation
- MaxPooling2D

### Convolution Block 3

- Conv2D (128 filters, 3×3 kernel)
- ReLU activation
- MaxPooling2D

### Convolution Block 4

- Conv2D (256 filters, 3×3 kernel)
- ReLU activation
- MaxPooling2D

### Flatten Layer

Converts the feature maps into a one-dimensional vector.

### Fully Connected Layer

- 256 Dense layer with ReLU activation

### Dropout Layer

Dropout was used to reduce overfitting. **Dropout = 0.7**

### Output Layer

The final layer uses: **Dense(1, activation=“sigmoid”)**

This is suitable for **binary classification**.

---

# Loss Function

The loss function used: **Binary Cross Entropy**

Optimizer used: **Adam Optimizer**

---

# Evaluation

The model performance was evaluated using the following metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

# Model Performance

### Final Classification Report

| Class   | Precision | Recall | F1-score |
| ------- | --------- | ------ | -------- |
| Cat (0) | 0.90      | 0.91   | 0.91     |
| Dog (1) | 0.91      | 0.90   | 0.91     |

Overall Accuracy: **0.91**

# Conclusion

The CNN model successfully classified cat and dog images with high accuracy.

The combination of convolutional layers, pooling layers, data augmentation, and dropout allowed the model to generalize well on unseen images.

This project demonstrates the effectiveness of CNNs for image classification tasks.
