# MNIST Digit Recognition using CNN Ensemble

## Project Overview
Implementation of Convolutional Neural Network (CNN) ensemble for MNIST digit recognition, achieving 99.65% accuracy (ranked ~100/2133 on Kaggle).

## Technical Architecture

### Data Processing Pipeline
- Normalization: Min-max scaling (0-1)
- Train-Validation Split: 80-20
- Data Augmentation: Flip, Rotation, Shift, Mean centering, ZCA whitening

### CNN Model Architecture
```python
Input → (28x28 pixels)
└── Conv1 [64 filters, 5x5 kernel] + ReLU + BatchNorm
    └── Conv2 [64 filters, 5x5 kernel] + ReLU + BatchNorm
        └── MaxPool [2x2] + Dropout(0.25)
            └── Conv3 [64 filters, 3x3 kernel] + ReLU + BatchNorm
                └── Conv4 [64 filters, 3x3 kernel] + ReLU + BatchNorm
                    └── MaxPool [2x2, stride=3] + Dropout(0.25)
                        └── Conv5 [64 filters, 3x3 kernel] + ReLU + BatchNorm
                            └── Dropout(0.25)
                                └── Flatten
                                    └── Dense(256) + ReLU + BatchNorm + Dropout(0.25)
                                        └── Softmax Output(10)
```
### Model Configuration
- Optimizer: RMSprop
- Learning rate: 0.001
- Rho: 0.9
- Epsilon: 1e-08
- Loss: Categorical Cross-entropy
- Epochs: 50

### Performance Metrics
Ensemble Results (5 Models)
| Model | Training Accuracy | Validation Accuracy | 
|-------|------------------|-------------------| 
| CNN 1 | 0.99845 | 0.99619 | 
| CNN 2 | 0.99839 | 0.99655 | 
| CNN 3 | 0.99839 | 0.99726 | 
| CNN 4 | 0.99833 | 0.99631 | 
| CNN 5 | 0.99764 | 0.99607 |

Final Kaggle Score: 0.99653

### Key Features

CNN Advantages
- Reduced parameter count vs traditional NN
- Spatial context preservation
- Enhanced feature extraction through convolution

Data Augmentation Benefits
- Improved model generalization
- Enhanced robustness to variations
- Better performance with limited data

Implementation Notes
- Interactive visualization tools for training data inspection
- Real-time prediction visualization on validation set
- Ensemble approach outperformed single NN sequential model
- Experimental full dataset training achieved 0.998 accuracy (non-competition compliant)

### References
- Kaggle Digit Recognizer Competition
- BUDT737 Course Materials
- Deep Learning Implementation Resources