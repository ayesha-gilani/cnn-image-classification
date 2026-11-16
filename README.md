
# Multi-Class Image Classification using CNN

A deep learning project that uses a Convolutional Neural Network (CNN) to classify images from the CIFAR-10 dataset into 10 different categories. The project focuses on building, training, evaluating, and improving a CNN model using TensorFlow and Keras.

## Project Overview

Image classification is a computer vision task in which a model learns to identify objects and assign them to predefined categories.

In this project, I developed a CNN model to classify CIFAR-10 images. I started with a baseline architecture and then improved the model using deeper convolutional blocks, batch normalization, dropout, and data augmentation.

The final model achieved **83.87% test accuracy**.

## Dataset

The project uses the **CIFAR-10 dataset**, a standard dataset for image classification research.

- **Total images:** 60,000
- **Training images:** 50,000
- **Testing images:** 10,000
- **Image dimensions:** 32 × 32 pixels
- **Image channels:** 3 (RGB)
- **Number of classes:** 10

### Classes

1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

## Model Architecture

The project uses a custom Convolutional Neural Network built with TensorFlow/Keras.

The improved architecture contains three convolutional blocks:

| Layer | Configuration |
|---|---|
| Block 1 | 2 × Conv2D (32 filters) + BatchNormalization + ReLU + MaxPooling + Dropout |
| Block 2 | 2 × Conv2D (64 filters) + BatchNormalization + ReLU + MaxPooling + Dropout |
| Block 3 | 2 × Conv2D (128 filters) + BatchNormalization + ReLU + MaxPooling + Dropout |
| Classification Head | Flatten + Dense (128) + BatchNormalization + Dropout |
| Output Layer | Dense (10) + Softmax |

### Techniques Used

- **Convolutional Layers:** Extract spatial features and patterns from images.
- **Batch Normalization:** Helps stabilize and speed up model training.
- **ReLU Activation:** Introduces non-linearity into the network.
- **Max Pooling:** Reduces feature-map dimensions.
- **Dropout:** Helps reduce overfitting.
- **Data Augmentation:** Applies random flipping, rotation, and zooming to improve generalization.
- **Softmax:** Produces class probabilities for the 10 output categories.

## Model Training

The model was trained using the following configuration:

| Parameter | Value |
|---|---|
| Framework | TensorFlow / Keras |
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Loss Function | Sparse Categorical Crossentropy |
| Evaluation Metric | Accuracy |
| Batch Normalization | Yes |
| Dropout | Yes |
| Data Augmentation | Random Flip, Rotation, Zoom |
| Early Stopping | Yes |
| Learning Rate Reduction | ReduceLROnPlateau |

Early stopping was used to restore the weights from the best validation performance. ReduceLROnPlateau was used to lower the learning rate when validation performance stopped improving.

## Model Performance

The improved CNN achieved the following results on the CIFAR-10 test dataset:

| Metric | Result |
|---|---:|
| Test Accuracy | **83.87%** |
| Test Loss | 0.4771 |
| Best Validation Accuracy | 84.73% |
| Best Validation Loss | 0.4557 |
| Total Parameters | 552,426 |
| Trainable Parameters | 551,274 |
| Non-Trainable Parameters | 1,152 |

### Training and Evaluation Visualizations

#### Accuracy Curve

![Accuracy Curve](assets/Accuracy%20Curve.PNG)

#### Loss Curve

![Loss Curve](assets/Loss%20Curve.PNG)

#### Confusion Matrix

![Confusion Matrix](assets/Confusion%20Matrix.PNG)

## Classification Report

The model was evaluated using precision, recall, and F1-score for each class.

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Airplane | 0.88 | 0.84 | 0.86 |
| Automobile | 0.91 | 0.94 | 0.93 |
| Bird | 0.85 | 0.73 | 0.78 |
| Cat | 0.79 | 0.67 | 0.72 |
| Deer | 0.79 | 0.82 | 0.80 |
| Dog | 0.81 | 0.74 | 0.77 |
| Frog | 0.75 | 0.94 | 0.83 |
| Horse | 0.86 | 0.88 | 0.87 |
| Ship | 0.93 | 0.91 | 0.92 |
| Truck | 0.84 | 0.92 | 0.88 |
| **Macro Average** | **0.84** | **0.84** | **0.84** |
| **Weighted Average** | **0.84** | **0.84** | **0.84** |

## Key Observations

- The model achieved its strongest F1-scores for automobiles and ships.
- Frog and automobile classes achieved particularly high recall.
- Cats and dogs were more challenging to classify, partly because of visual similarities.
- The confusion matrix helped identify classes where the model made incorrect predictions.
- Data augmentation and regularization techniques improved the model's generalization performance.

## Limitations

- CIFAR-10 images have a relatively low resolution of 32 × 32 pixels.
- The model is limited to the 10 categories included in the dataset.
- Visually similar categories, such as cats and dogs, can be difficult to distinguish.
- Performance on real-world images may differ because of changes in image quality, backgrounds, lighting, and object appearance.
- The model cannot reliably classify categories outside its training classes.

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

## Project Structure

```text
cnn-image-classification/
│
├── assets/
│   ├── Accuracy Curve.PNG
│   ├── Loss Curve.PNG
│   └── Confusion Matrix.PNG
│
├── model/
│   └── cifar10_cnn_model.keras
│
├── Multi_Class_Image_Classification_CNN.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

## Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/ayesha-gilani/cnn-image-classification.git
```

### 2. Navigate to the Project Directory

```bash
cd cnn-image-classification
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Notebook

Open the notebook in Jupyter or Google Colab:

`Multi_Class_Image_Classification_CNN.ipynb`

Run the cells sequentially to load the dataset, preprocess images, train the model, and evaluate its performance.

## Future Improvements

- Experiment with deeper CNN architectures.
- Explore transfer learning using pretrained models.
- Apply hyperparameter tuning.
- Investigate class-specific performance improvements.
- Test the model on additional real-world images.

## Conclusion

This project provided practical experience in developing a complete image classification pipeline using CNNs.

Starting with a baseline model and improving its architecture through batch normalization, dropout, and data augmentation helped achieve **83.87% test accuracy** on CIFAR-10.

It also provided hands-on experience with model training, performance evaluation, confusion matrices, classification metrics, and deep learning workflows.

## Author

**Ayesha Gilani**


*Developed as part of an AI/ML internship task.*
