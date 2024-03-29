# S9---Assignment

## Architecture

Base Architecture: The model is based on the C1C2C3C40 architecture, which traditionally uses max pooling for downsampling.

Modifications:

Convolutional Layer Modification: Instead of max pooling, the model uses three convolutional layers with 3x3 filters and a stride of 2 for downsampling. This change helps in reducing spatial dimensions while enhancing feature complexity.

Final Layer Utilization: The final layer of the model utilizes global average pooling (GAP) instead of traditional fully connected layers. GAP simplifies feature consolidation by computing the average of all values across the feature maps.

Special Convolutional Techniques:

Depthwise Separable Convolution: One layer employs depthwise separable convolution, which decomposes the standard convolution into depthwise and pointwise convolutions, optimizing computation and parameters.

Dilated Convolution: Another layer uses dilated convolution to expand the receptive field of neurons without increasing parameters, allowing the model to capture broader contextual information.

Purpose: The model leverages these modifications to improve efficiency, reduce overfitting, and enhance the model's ability to capture complex features, making it suitable for various classification tasks.

## Model summary

----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Conv2d-1           [-1, 32, 32, 32]             864
              ReLU-2           [-1, 32, 32, 32]               0
       BatchNorm2d-3           [-1, 32, 32, 32]              64
            Conv2d-4          [-1, 192, 32, 32]           6,144
              ReLU-5          [-1, 192, 32, 32]               0
       BatchNorm2d-6          [-1, 192, 32, 32]             384
            Conv2d-7          [-1, 192, 32, 32]           1,728
              ReLU-8          [-1, 192, 32, 32]               0
       BatchNorm2d-9          [-1, 192, 32, 32]             384
           Conv2d-10           [-1, 32, 32, 32]           6,144
             ReLU-11           [-1, 32, 32, 32]               0
      BatchNorm2d-12           [-1, 32, 32, 32]              64
           Conv2d-13           [-1, 32, 16, 16]           9,216
      BatchNorm2d-14           [-1, 32, 16, 16]              64
           Conv2d-15          [-1, 192, 16, 16]           6,144
             ReLU-16          [-1, 192, 16, 16]               0
      BatchNorm2d-17          [-1, 192, 16, 16]             384
           Conv2d-18          [-1, 192, 16, 16]           1,728
             ReLU-19          [-1, 192, 16, 16]               0
      BatchNorm2d-20          [-1, 192, 16, 16]             384
           Conv2d-21           [-1, 32, 16, 16]           6,144
             ReLU-22           [-1, 32, 16, 16]               0
      BatchNorm2d-23           [-1, 32, 16, 16]              64
           Conv2d-24             [-1, 32, 8, 8]           9,216
      BatchNorm2d-25             [-1, 32, 8, 8]              64
           Conv2d-26            [-1, 192, 8, 8]           6,144
             ReLU-27            [-1, 192, 8, 8]               0
      BatchNorm2d-28            [-1, 192, 8, 8]             384
           Conv2d-29            [-1, 192, 8, 8]           1,728
             ReLU-30            [-1, 192, 8, 8]               0
      BatchNorm2d-31            [-1, 192, 8, 8]             384
           Conv2d-32             [-1, 64, 8, 8]          12,288
             ReLU-33             [-1, 64, 8, 8]               0
      BatchNorm2d-34             [-1, 64, 8, 8]             128
           Conv2d-35             [-1, 64, 8, 8]           2,048
      BatchNorm2d-36             [-1, 64, 8, 8]             128
           Conv2d-37             [-1, 64, 4, 4]          36,864
      BatchNorm2d-38             [-1, 64, 4, 4]             128
           Conv2d-39            [-1, 384, 4, 4]          24,576
             ReLU-40            [-1, 384, 4, 4]               0
      BatchNorm2d-41            [-1, 384, 4, 4]             768
           Conv2d-42            [-1, 384, 4, 4]           3,456
             ReLU-43            [-1, 384, 4, 4]               0
      BatchNorm2d-44            [-1, 384, 4, 4]             768
           Conv2d-45            [-1, 132, 4, 4]          50,688
             ReLU-46            [-1, 132, 4, 4]               0
      BatchNorm2d-47            [-1, 132, 4, 4]             264
           Conv2d-48            [-1, 132, 4, 4]           8,448
      BatchNorm2d-49            [-1, 132, 4, 4]             264
        AvgPool2d-50            [-1, 132, 1, 1]               0
           Linear-51                   [-1, 10]           1,330
================================================================
Total params: 199,970
Trainable params: 199,970
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.01
Forward/backward pass size (MB): 14.19
Params size (MB): 0.76
Estimated Total Size (MB): 14.97
----------------------------------------------------------------

## Data augmentation / albumentation transformations

Horizontal Flipping: This technique involves flipping the images horizontally, effectively mirroring them along the vertical axis. By doing so, it introduces variations in the orientation of objects within the images, which can help the model generalize better to unseen data.

ShiftScaleRotate: This technique encompasses a combination of three transformations: shifting, scaling, and rotating the images. Shifting involves moving the image along its x and y axes, scaling adjusts its size, and rotating changes its orientation. These transformations simulate real-world variations in object position, size, and orientation, thereby making the model more resilient to such changes during inference.

Coarse Dropout: Coarse dropout involves randomly masking out rectangular regions within the images by setting their pixel values to zero. This introduces localized occlusions in the images, effectively forcing the model to focus on other relevant features. By doing so, it encourages the model to learn more robust and invariant representations of objects, thus improving its generalization ability.

![image](https://github.com/harikishanm96/S9---Assignment/assets/53985105/05cae4b1-10e2-451f-b0a0-90b0964dc1c2)

## Accuracy

Train accuracy: 80.82%

Test accuracy: 84.77%

## Per class accuracy

Accuracy of plane : 84 %

Accuracy of   car : 96 %

Accuracy of  bird : 70 %

Accuracy of   cat : 62 %

Accuracy of  deer : 82 %

Accuracy of   dog : 80 %

Accuracy of  frog : 92 %

Accuracy of horse : 92 %

Accuracy of  ship : 84 %

Accuracy of truck : 97 %


