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
