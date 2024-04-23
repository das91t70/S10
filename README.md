## S10 - Residual Connections in CNNs and One Cycle Policy

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

