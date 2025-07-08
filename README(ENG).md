# Automatic Parasite Detection in Microscopic Cell Images Using CNN

This project aims to automatically detect whether microscope cell images contain parasites using a CNN (Convolutional Neural Network) model. Each colored image has dimensions of 103x103 pixels with 3 channels (RGB). Labels are binary: 0 for clean cells and 1 for parasite-infected cells. Due to fixed input size requirements for CNN, all images were resized to 224x224.

The model architecture is inspired by LeNet: two Conv2D layers extract features such as edges, colors, and textures, followed by Batch Normalization to stabilize training and MaxPooling for dimensionality reduction. The data is then flattened and passed through two Dense layers, with a single sigmoid neuron for binary classification at the output.

BinaryCrossentropy loss and Adam optimizer were used during training. Model performance was evaluated using F1 score and AUC–ROC metrics. The AUC–ROC curve indicates the model's ability to distinguish classes, with values closer to 1 representing stronger models. Predictions above 0.5 are classified as parasite-infected cells, and those below or equal to 0.5 as clean cells.

# Technologies and Libraries Used
TensorFlow / Keras — Deep learning and CNN modeling

NumPy — Data processing

OpenCV — Image processing and resizing

Scikit-learn — Model evaluation metrics

Matplotlib — Visualization of results

# PROJECT FLOWS
# 1- Data Preparation
Microscope images sized 103x103 RGB were resized to 224x224 for CNN input.

# 2- Model Design
Built a LeNet-like model with 2 Conv2D layers, BatchNorm, MaxPool, Flatten, 2 Dense layers, and sigmoid output.

# 3- Model Training
Trained using BinaryCrossentropy loss and Adam optimizer.

# 4- Evaluation
Measured performance with F1 score and AUC-ROC metrics.

# 5- Classification
Output > 0.5 classified as parasite-infected; ≤ 0.5 as clean cells.


# File Structure
├── data/                  # Cell images and labels  
├── model/                 # Trained model files  
├── scripts/               # Training and evaluation scripts  
├── README.md              # Project description  
└── requirements.txt       # Required libraries  


# Future Improvements

Use deeper CNN architectures or transfer learning

Apply data augmentation for better generalization

Extend to multi-class classification for different parasite types

# Product Owner
Çağdaş ÇANKAYA
