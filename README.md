# Household Animals Classification Using Deep Learning

A deep learning project that classifies household animal images into two categories: **Cat** and **Dog**. This project compares a custom VGG-like Convolutional Neural Network (CNN), a regularized CNN, and a pretrained VGG16 model using transfer learning and fine-tuning.

## Project Overview

The objective is to build and evaluate image classification models and compare their performance on a Cats vs Dogs dataset.

The project explores how data augmentation, dropout, transfer learning, and fine-tuning can improve image classification accuracy and reduce overfitting.

## Models Implemented

1. **VGG-like CNN (Baseline)**  
   A custom CNN trained from scratch using convolutional layers, ReLU activations, max pooling, and dense layers.

2. **Regularized CNN**  
   The baseline architecture enhanced with random horizontal flipping and dropout (0.5) to improve generalization.

3. **VGG16 Transfer Learning**  
   An ImageNet-pretrained VGG16 model with a frozen convolutional base and a custom classification head.

4. **VGG16 Fine-tuning**  
   The pretrained model is further trained by unfreezing layers from `block5_conv1` using a low learning rate.

## Dataset

- **Dataset:** Microsoft Cats vs Dogs archive.
- **Total usable images:** 24,998.
- **Cat images:** 12,499.
- **Dog images:** 12,499.
- **Image size:** 224 × 224 pixels.
- **Batch size:** 32.

### Dataset Split

| Split | Images per class | Total images |
|---|---:|---:|
| Training | 9,999 | 19,998 |
| Validation | 2,000 | 4,000 |
| Testing | 500 | 1,000 |
| **Total** | **12,499** | **24,998** |

Images are validated, converted to RGB JPEG format, and organized into training, validation, and testing sets.

*Note: The implementation uses the Microsoft Cats vs Dogs archive because the Kaggle competition download was unavailable in the working environment.*

## Technologies Used

- Python
- TensorFlow and Keras
- NumPy
- Matplotlib
- Pillow (PIL)
- Scikit-learn
- Jupyter Notebook / Google Colab
- VGG16 and Convolutional Neural Networks

## Model Training

The models use binary cross-entropy as the loss function and RMSprop as the optimizer. The classification labels are:

- `Cat = 0`
- `Dog = 1`

The workflow includes dataset validation, preprocessing, model training, data augmentation, transfer learning, fine-tuning, and performance evaluation.

## Results

The following results were obtained during the reported experiment.

| Model | Test Loss | Test Accuracy |
|---|---:|---:|
| VGG-like CNN baseline | 1.6643 | 85.10% |
| Dropout + augmentation CNN | 0.1856 | 92.20% |
| VGG16 transfer learning | 0.1036 | 98.40% |
| **VGG16 fine-tuned** | **0.0951** | **98.60%** |

The fine-tuned VGG16 model achieved the best test accuracy of **98.60%**, improving on the frozen transfer-learning model by 0.20 percentage points.

## Visualizations and Interpretability

The project includes:

- Training and validation accuracy curves.
- Training and validation loss curves.
- Intermediate convolutional activation visualizations.
- Grad-CAM heatmaps to visualize image regions influencing a prediction.

These visualizations help analyze model learning, possible overfitting, and the regions associated with model predictions.

## How to Run the Project

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>
```

Replace the placeholders with your actual GitHub repository URL and folder name.

### 2. Install the dependencies

```bash
pip install tensorflow numpy matplotlib pillow scikit-learn jupyter
```

### 3. Open the notebook

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `Household_Animals_Classification.ipynb` and execute the cells in order.

Alternatively, upload the notebook to Google Colab and run it there.

### 4. Dataset setup

The notebook downloads and extracts the Microsoft Cats vs Dogs archive when the expected dataset folders are unavailable. Ensure that you have an internet connection and sufficient storage space.

### 5. Train and evaluate

Run the notebook cells sequentially to validate the images, prepare the dataset splits, train the models, evaluate test performance, and generate visualizations.

**Note:** Training time and results may vary depending on the hardware, dataset state, and execution environment. The reported accuracy values correspond to the documented experiment and are not guaranteed on every run.

## Future Improvements

- Generate a confusion matrix.
- Evaluate precision, recall, and F1-score.
- Test the models on independently collected images.
- Investigate duplicate images and potential dataset bias.
- Repeat experiments with different random seeds.
- Explore additional architectures and hyperparameter tuning.

## Conclusion

This project demonstrates that transfer learning can outperform a CNN trained from scratch on a binary image classification task. Fine-tuning the pretrained VGG16 model achieved the highest reported test accuracy of **98.60%**.

The experiment also highlights the value of regularization, data augmentation, and model interpretability when developing deep learning applications.

## Team Members

- **D. Harikrishnan**
- **Dhanush K. S.**

## Reference

Lei Lin, *Household Animals Classification Using Deep Learning*, CS229 Spring 2020 project report. The implementation described here uses the Microsoft Cats vs Dogs archive.

---

**Project:** Household Animals Classification Using Deep Learning  
**Domain:** Machine Learning / Deep Learning  
**Task:** Binary Image Classification  
**Best Reported Test Accuracy:** 98.60%
