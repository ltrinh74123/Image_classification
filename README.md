# Image_classification

### CNN Architecture

For this application I went with this model architecture:

#### CNN Layers
1. **Convolutional Layer (5×5 kernel, 32 filters)** applies 32 filters to extract features such as edges, curves, and textures from the input image. The 5×5 kernel helps capture broader spatial patterns, and using more filters allows for diverse feature extraction.

2. **Max Pooling Layer (2×2)** reduces the spatial dimensions of the feature maps by half, preserving the most significant features while reducing computation.

3. **Convolutional Layer (3×3 kernel, 64 filters)** applies 64 filters with smaller 3×3 kernels to capture more fine-grained and local features. The higher number of filters enhances the model’s capacity to learn complex patterns.

5. **Max Pooling Layer (2×2)** downsamples the feature maps to reduce dimensionality and computational cost, while retaining essential features.

6. **Flatten Layer** converts the 2D feature maps into a 1D feature vector, preparing the data for input into the dense (fully connected) layers.

9. **Dense Layer (64 units, ReLU activation)** is a fully connected layer with 64 neurons that learns higher-level representations by combining extracted features. Each neuron applies a weighted sum followed by a ReLU activation.

10. **Output Dense Layer (10 units, Softmax activation)** consists of 10 neurons—one for each class in the dataset. It outputs class probabilities using the softmax activation function.


### Activation functions
- Relu Activation function is used in the hidden layers to introduce non-linearity and mitigate the vanishing gradient problem, enabling the network to learn complex relationships.
- Softmax output Activation function is used in the output layer to convert raw scores into a probability distribution. This ensures the probability outputs sum to 1, making it suitable for multi-class classification.
