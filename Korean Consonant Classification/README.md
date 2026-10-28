# Korean Consonant Classification

## Project Overview

A deep learning project focused on classifying handwritten Korean consonants using neural networks.

The project explores and compares Multilayer Perceptron (MLP) and Convolutional Neural Network (CNN) architectures to identify effective model configurations for image classification.

## Objectives

- Develop neural networks for Korean consonant classification.
- Implement image preprocessing and data augmentation.
- Compare MLP and CNN architectures.
- Experiment with different learning rates.
- Evaluate model performance using accuracy and loss.
- Select and save the best-performing model for testing.

## Dataset

The dataset contains images representing 14 Korean consonants:

ㄱ, ㄴ, ㄷ, ㄹ, ㅁ, ㅂ, ㅅ, ㅇ, ㅈ, ㅊ, ㅋ, ㅌ, ㅍ, ㅎ

**Data preparation:**
- Converted images to grayscale.
- Cropped and centered consonant images.
- Resized images to 64 × 64 pixels.
- Applied normalization and data augmentation.
- Used 84 training images and 28 validation images, separated by writer.

## Model Architectures

### Multilayer Perceptron (MLP)
- Input: 64 × 64 grayscale images
- Fully connected layers with 256 and 128 hidden units
- ReLU activation functions
- Output: 14 consonant classes

### Convolutional Neural Network (CNN)
- Two convolutional layers
- ReLU activation functions
- Max pooling and adaptive average pooling
- Fully connected classification layers
- Output: 14 consonant classes

## Training Configuration

- **Framework:** PyTorch
- **Optimizer:** Adam
- **Loss Function:** Cross-Entropy Loss
- **Batch Size:** 16
- **Training Epochs:** 50 per configuration
- **Learning Rate Scheduler:** StepLR

Four model configurations were evaluated using different architectures and learning rates.

## Results

| Model | Learning Rate | Best Validation Accuracy |
|---|---|---|
| MLP | 0.001 | 78.57% |
| MLP | 0.0005 | 82.14% |
| CNN | 0.001 | 64.29% |
| CNN | 0.0003 | 60.71% |

**Best Model: MLP**

- Learning Rate: 0.0005
- Best Validation Accuracy: 82.14%
- Best Epoch: 42

The selected MLP configuration achieved the highest validation accuracy among the four evaluated configurations.

The selected architecture was subsequently trained on the complete available training dataset, and its checkpoint was saved as `best_model.pth`.

*Note: Validation accuracy is reported here. Final test-set accuracy is not included because it has not been recorded in the provided testing notebook.*

## Testing

The testing notebook loads the saved model checkpoint and evaluates predictions against ground-truth labels.

The testing process includes:
- Loading the trained model
- Preprocessing test images
- Generating predictions
- Comparing predictions with ground-truth labels
- Calculating overall classification accuracy

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy / Matplotlib for the broader deep learning workflow
- Pillow (PIL)
- Jupyter Notebook / Google Colab

## Project Files

| File | Description |
|---|---|
| `midterm_training.ipynb` | Data preprocessing, model training, comparison, and visualization |
| `midterm_test.ipynb` | Model loading and test accuracy evaluation |
| `best_model.pth` | Saved trained model checkpoint |

## How to Run

1. Open `midterm_training.ipynb` in Google Colab.
2. Provide the required training dataset as `dataset.zip` or a `dataset` directory.
3. Run the notebook to train and compare the models.
4. Save the generated `best_model.pth` checkpoint.
5. Open `midterm_test.ipynb`.
6. Provide `best_model.pth`, the `test_set` directory, and `test_labels.txt`.
7. Run the notebook to evaluate test-set accuracy.

The dataset and test labels are required to reproduce the results.

## Project Context

Developed as part of undergraduate artificial intelligence coursework, this project provided practical experience in neural network implementation, image preprocessing, model training, hyperparameter comparison, and performance evaluation.
