# Deepfake Detection using Inception-V3 and RNN network


This code was submitted on a [Kaggle competition](https://www.kaggle.com/c/deepfake-detection-challenge).

### Dataset:
The full training set is just over 470 GB. You must accept the competition's rules to gain access to the dataset.
The dataset can be downloaded from the [competition site](https://www.kaggle.com/c/deepfake-detection-challenge/data) or using Kaggle API as shown below.

```kaggle competitions download -c deepfake-detection-challenge```

### Face Detection:
BlazeFace is a fast, light-weight face detector from Google Research.
Weights of BlazeFace implemented in PyTorch is taken from this [Kaggle dataset.](https://www.kaggle.com/humananalog/blazeface-pytorch)
PyTorch implementation of BlazeFace is demonstrated in this [GitHub repository.](https://github.com/hollance/BlazeFace-PyTorch)

### Reference Paper:
David G¨uera, Edward J. Delp. [Deepfake Video Detection Using Recurrent Neural Networks](https://arxiv.org/abs/1609.07910)

