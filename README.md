## Deepfake Detection Challenge (Kaggle)
This is a Kaggle competition, to identify videos with facial and voice manipulations. Over two thousand teams participated in this Deepfake Detection Challenge (DFDC). Log Loss metric is used for evaluating the model performance and getting a rank in the leaderboard.

### Dataset
The full training set is just over 470 GB. You must accept the competition's rules to gain access to the dataset.

The dataset can be downloaded from the [competition site](https://www.kaggle.com/c/deepfake-detection-challenge/data) or using Kaggle API as shown below.<br>
```kaggle competitions download -c deepfake-detection-challenge```

## Solution Description

### Deepfake Detection using Inception-V3 and RNN network

This code was submitted on [Kaggle's Deepfake Detection Challenge](https://www.kaggle.com/c/deepfake-detection-challenge). The model is trained on only 4 GB dataset which is directly available on Kaggle. Achieved a log loss of 1.05. This can be reduced to a great extent by training the dataset on entire 470 GB dataset.

### Prerequisites
- OpenCV 4.1.2
- NumPy 1.17.4
- Pandas 0.25.3
- PyTorch 1.3.0
- Tensorflow 2.1.0-rc0

### Procedure
- Oversampling (for handling class-imbalance problem as 77 real and 323 fake labels in the 4 GB dataset on Kaggle).
- Captured 20 continuous frames from each video.
- Extracted the best possible face (ROI) from each frame using BlazeFace PyTorch.
- Isotropically resized the ROI for keeping the aspect ratio intact.
- Zero-padded if required.
- Pre-padded the input sequences for a constant timestep (in case face is not detected in a particular frame).
- NumPy array of shape (batch_size, 20, 299, 299, 3) is formed and sent to Inception-V3 for feature extraction.
- Further the extracted features are sent to RNN for exploiting temporal inconsistencies.

### Face Detection Technique
BlazeFace is a fast, light-weight face detector from Google Research.<br>
Weights of BlazeFace (implemented in PyTorch) are loaded from this [Kaggle dataset](https://www.kaggle.com/humananalog/blazeface-pytorch).

For reference, PyTorch implementation of BlazeFace is demonstrated in this [GitHub repository](https://github.com/hollance/BlazeFace-PyTorch).

### Future work
- [ ] Sort by Histogram in case of multiple faces in a video. 
- [ ] ResNeXt.
- [ ] Xception network.
- [ ] EfficientNet.
- [ ] Handle voice manipulations (spectrogram).

### References
- David Güera, Edward J. Delp. [Deepfake Video Detection Using Recurrent Neural Networks](https://ieeexplore.ieee.org/document/8639163).
- [Kaggle kernel](https://www.kaggle.com/c/deepfake-detection-challenge/notebooks) for face extraction and image pre-processing.
