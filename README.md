## Deepfake-Detection-Challenge
This is a Kaggle competition, to identify videos with facial and voice manipulations. Over two thousand teams participated in this Deepfake Detection Challenge (DFDC). Log Loss metric is used for evaluating the model performance and getting a rank in the leaderboard.

### Dataset
The full training set is just over 470 GB. You must accept the competition's rules to gain access to the dataset.

The dataset can be downloaded from the [competition site](https://www.kaggle.com/c/deepfake-detection-challenge/data) or using Kaggle API as shown below.<br>
```kaggle competitions download -c deepfake-detection-challenge```

### Face Detection
BlazeFace is a fast, light-weight face detector from Google Research.<br>
Weights of BlazeFace (implemented in PyTorch) are loaded from this [Kaggle dataset](https://www.kaggle.com/humananalog/blazeface-pytorch).

For reference, PyTorch implementation of BlazeFace is demonstrated in this [GitHub repository](https://github.com/hollance/BlazeFace-PyTorch).

# Methods
- [x] Extracting ROI using BlazeFace PyTorch.
- [x] CNN (Inception-V3) for feature extraction.
- [x] Handling imbalanced dataset (oversampling).
- [x] Implementing a recurrent neural network.
- [ ] ResNeXt.
- [ ] Xception.
- [ ] EfficientNet.
- [ ] Handle voice manipulations.
