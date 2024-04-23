## S10 - Residual Connections in CNNs and One Cycle Policy

### Project Structure
* S10.ipynb - uses classes and functions in [main](https://github.com/das91t70/TSAIV2Main) repo which has code for performing transformations ( data augmentation), data load, train and test the data, compute learning rate using LR finder. As part of this notebook, we use those classes and functions to load CIFAR10 data , train and test the model to achieve desired accuracy.

### Project Structure in main repo for S10
* [custom_resnet.py](https://github.com/das91t70/TSAIV2Main/blob/main/S10/custom_resnet.py) - has custom resnet network with conv and resnet blocks with kernels ( 64, 128, 256 ).
* [load_and_visualize_data.py](https://github.com/das91t70/TSAIV2Main/blob/main/S10/load_and_visualize_data.py) - defines CIFAR10DataOps class that provides functions for loading CIFAR10 dataset, performing transformations ( RandomCrop, FlipLR, Cutout) and create dataloader instance. function to visualize data in a batch is also provided.
* [train_test_utils](https://github.com/das91t70/TSAIV2Main/blob/main/S10/train_test_utils.py) - defines TrainTestUtils class which offers functions to train, test the model and compute loss and accuracy graphs for training ans testing data. It also offers functions to compute maximum learning rate using range test ( fastai and leslie smith) 

#### Target:
    Accuracy - 90%
    No of Epochs - 24
    Max learning rate to be achieved at Epoch 5
    Use OneCycleLR scheduler
    Compute maximum learning rate using pytorch LR finder
    Use image augmentation ( RandomCrop, FlipLR, Cutout)

#### Result:
    No of parameters of model: 6.57 million
    Test Accuracy: 91.87%
    Trained for 24 epochs and with maximum learning rate 0.0008 (found at steepest gradient)

#### Analysis:

    Model is heavy as we are using kernels of ( 64, 128, 256 ) count. 
    Model is prone to overfitting.
    When maximum learning rate is taken at lowest loss then test accuracy seems to be better ( 92.56%) than the maximum learning rate taken at steepest gradient.
    Usage of OneCycleLR helped to achieve target accuracy faster.

