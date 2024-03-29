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

![image](https://github.com/harikishanm96/S9---Assignment/assets/53985105/e868873e-e39c-4743-b91a-3f972f5c2e68)

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

## Logs

Epoch: 0,Loss=1.36 Batch_id=390 Accuracy=43.77: 100%|██████████| 391/391 [00:22<00:00, 17.39it/s]
Test set: Average loss: 0.0103, Accuracy: 5502/10000 (55.02%)

Epoch: 1,Loss=1.01 Batch_id=390 Accuracy=56.76: 100%|██████████| 391/391 [00:18<00:00, 20.71it/s]
Test set: Average loss: 0.0074, Accuracy: 6703/10000 (67.03%)

Epoch: 2,Loss=1.15 Batch_id=390 Accuracy=62.66: 100%|██████████| 391/391 [00:18<00:00, 21.39it/s]
Test set: Average loss: 0.0068, Accuracy: 6987/10000 (69.87%)

Epoch: 3,Loss=0.79 Batch_id=390 Accuracy=66.21: 100%|██████████| 391/391 [00:19<00:00, 20.03it/s]
Test set: Average loss: 0.0062, Accuracy: 7274/10000 (72.74%)

Epoch: 4,Loss=0.80 Batch_id=390 Accuracy=68.51: 100%|██████████| 391/391 [00:18<00:00, 21.38it/s]
Test set: Average loss: 0.0055, Accuracy: 7595/10000 (75.95%)

Epoch: 5,Loss=1.09 Batch_id=390 Accuracy=70.12: 100%|██████████| 391/391 [00:18<00:00, 21.60it/s]
Test set: Average loss: 0.0053, Accuracy: 7682/10000 (76.82%)

Epoch: 6,Loss=0.77 Batch_id=390 Accuracy=75.17: 100%|██████████| 391/391 [00:19<00:00, 19.78it/s]
Test set: Average loss: 0.0043, Accuracy: 8107/10000 (81.07%)

Epoch: 7,Loss=0.74 Batch_id=390 Accuracy=76.07: 100%|██████████| 391/391 [00:19<00:00, 20.35it/s]
Test set: Average loss: 0.0041, Accuracy: 8183/10000 (81.83%)

Epoch: 8,Loss=0.62 Batch_id=390 Accuracy=76.95: 100%|██████████| 391/391 [00:18<00:00, 20.86it/s]
Test set: Average loss: 0.0040, Accuracy: 8232/10000 (82.32%)

Epoch: 9,Loss=0.57 Batch_id=390 Accuracy=77.55: 100%|██████████| 391/391 [00:19<00:00, 20.21it/s]
Test set: Average loss: 0.0040, Accuracy: 8224/10000 (82.24%)

Epoch: 10,Loss=0.81 Batch_id=390 Accuracy=78.00: 100%|██████████| 391/391 [00:18<00:00, 21.23it/s]
Test set: Average loss: 0.0039, Accuracy: 8290/10000 (82.90%)

Epoch: 11,Loss=0.65 Batch_id=390 Accuracy=78.32: 100%|██████████| 391/391 [00:18<00:00, 21.46it/s]
Test set: Average loss: 0.0039, Accuracy: 8318/10000 (83.18%)

Epoch: 12,Loss=0.66 Batch_id=390 Accuracy=79.53: 100%|██████████| 391/391 [00:19<00:00, 20.55it/s]
Test set: Average loss: 0.0037, Accuracy: 8379/10000 (83.79%)

Epoch: 13,Loss=0.57 Batch_id=390 Accuracy=79.69: 100%|██████████| 391/391 [00:19<00:00, 20.48it/s]
Test set: Average loss: 0.0036, Accuracy: 8407/10000 (84.07%)

Epoch: 14,Loss=0.65 Batch_id=390 Accuracy=80.15: 100%|██████████| 391/391 [00:18<00:00, 21.48it/s]
Test set: Average loss: 0.0036, Accuracy: 8411/10000 (84.11%)

Epoch: 15,Loss=0.55 Batch_id=390 Accuracy=79.88: 100%|██████████| 391/391 [00:19<00:00, 20.31it/s]
Test set: Average loss: 0.0036, Accuracy: 8418/10000 (84.18%)

Epoch: 16,Loss=0.53 Batch_id=390 Accuracy=80.23: 100%|██████████| 391/391 [00:18<00:00, 21.17it/s]
Test set: Average loss: 0.0036, Accuracy: 8430/10000 (84.30%)

Epoch: 17,Loss=0.64 Batch_id=390 Accuracy=80.00: 100%|██████████| 391/391 [00:19<00:00, 20.49it/s]
Test set: Average loss: 0.0036, Accuracy: 8453/10000 (84.53%)

Epoch: 18,Loss=0.62 Batch_id=390 Accuracy=80.23: 100%|██████████| 391/391 [00:18<00:00, 21.04it/s]
Test set: Average loss: 0.0036, Accuracy: 8461/10000 (84.61%)

Epoch: 19,Loss=0.53 Batch_id=390 Accuracy=80.69: 100%|██████████| 391/391 [00:18<00:00, 21.36it/s]
Test set: Average loss: 0.0035, Accuracy: 8455/10000 (84.55%)

Epoch: 20,Loss=0.58 Batch_id=390 Accuracy=80.60: 100%|██████████| 391/391 [00:19<00:00, 20.36it/s]
Test set: Average loss: 0.0036, Accuracy: 8456/10000 (84.56%)

Epoch: 21,Loss=0.43 Batch_id=390 Accuracy=80.75: 100%|██████████| 391/391 [00:19<00:00, 20.30it/s]
Test set: Average loss: 0.0035, Accuracy: 8462/10000 (84.62%)

Epoch: 22,Loss=0.65 Batch_id=390 Accuracy=80.76: 100%|██████████| 391/391 [00:18<00:00, 21.38it/s]
Test set: Average loss: 0.0036, Accuracy: 8452/10000 (84.52%)

Epoch: 23,Loss=0.53 Batch_id=390 Accuracy=80.69: 100%|██████████| 391/391 [00:19<00:00, 20.56it/s]
Test set: Average loss: 0.0036, Accuracy: 8452/10000 (84.52%)

Epoch: 24,Loss=0.61 Batch_id=390 Accuracy=80.47: 100%|██████████| 391/391 [00:18<00:00, 21.70it/s]
Test set: Average loss: 0.0036, Accuracy: 8441/10000 (84.41%)

Epoch: 25,Loss=0.40 Batch_id=390 Accuracy=80.72: 100%|██████████| 391/391 [00:18<00:00, 20.96it/s]
Test set: Average loss: 0.0035, Accuracy: 8447/10000 (84.47%)

Epoch: 26,Loss=0.55 Batch_id=390 Accuracy=80.80: 100%|██████████| 391/391 [00:18<00:00, 21.34it/s]
Test set: Average loss: 0.0035, Accuracy: 8462/10000 (84.62%)

Epoch: 27,Loss=0.70 Batch_id=390 Accuracy=80.82: 100%|██████████| 391/391 [00:18<00:00, 21.46it/s]
Test set: Average loss: 0.0035, Accuracy: 8453/10000 (84.53%)

Epoch: 28,Loss=0.48 Batch_id=390 Accuracy=80.66: 100%|██████████| 391/391 [00:19<00:00, 20.36it/s]
Test set: Average loss: 0.0036, Accuracy: 8477/10000 (84.77%)

Epoch: 29,Loss=0.59 Batch_id=390 Accuracy=80.81: 100%|██████████| 391/391 [00:18<00:00, 21.60it/s]
Test set: Average loss: 0.0035, Accuracy: 8450/10000 (84.50%)

## Misclassified images

![image](https://github.com/harikishanm96/S9---Assignment/assets/53985105/aab26666-efc9-4663-9dc4-ad9861ab9ffc)




