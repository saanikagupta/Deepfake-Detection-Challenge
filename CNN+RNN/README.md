## Deepfake Detection using Inception-V3 and RNN network

This code was submitted on [Kaggle's Deepfake Detection Challenge](https://www.kaggle.com/c/deepfake-detection-challenge). The model is trained on only 4 GB dataset directly available on Kaggle. Achieved a log loss of 1.05. This can be reduced to a great extent by training the dataset on entire 470 GB dataset.

### Prerequisites
- OpenCV 4.1.2
- NumPy 1.17.4
- Pandas 0.25.3
- PyTorch 1.3.0
- Tensorflow 2.1.0-rc0

### Steps
- Oversampling (for handling class-imbalance problem as 77 real and 323 fake labels in the 4 GB dataset on Kaggle).
- Captured 20 continuous frames from each video.
- Extracted the best possible face (ROI) from each frame using BlazeFace PyTorch.
- Isotropically resized the ROI for keeping the aspect ratio intact.
- Zero-padded if required.
- Pre-padded in case face is not detected in a particular frame.
- NumPy array of shape (batch_size, 20, 299, 299, 3) is formed and sent to Inception-V3 for feature extraction.
- Further the extracted features are sent to RNN for exploiting temporal inconsistencies.

### Reference Paper
David G¨uera, Edward J. Delp. [Deepfake Video Detection Using Recurrent Neural Networks](https://arxiv.org/abs/1609.07910).
