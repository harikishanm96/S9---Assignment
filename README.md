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
