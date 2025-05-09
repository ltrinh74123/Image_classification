# Image classification

### Baseline CNN Architecture

For this application I started with this baseline so I could see how it performs:

#### CNN Layers

1. **Convolutional Layer (5×5 kernel, 32 filters)** applies 32 filters to extract features such as edges, curves, and textures from the input image. The 5×5 kernel helps capture broader spatial patterns, and using more filters allows for diverse feature extraction.

2. **Max Pooling Layer (2×2)** reduces the spatial dimensions of the feature maps by half, preserving the most significant features while reducing computation.

3. **Convolutional Layer (3×3 kernel, 64 filters)** applies 64 filters with smaller 3×3 kernels to capture more fine-grained and local features. The higher number of filters enhances the model’s capacity to learn complex patterns.

4. **Max Pooling Layer (2×2)** downsamples the feature maps to reduce dimensionality and computational cost, while retaining essential features.

5. **Flatten Layer** converts the 2D feature maps into a 1D feature vector, preparing the data for input into the dense (fully connected) layers.

6. **Dense Layer (64 units, ReLU activation)** is a fully connected layer with 64 neurons that learns higher-level representations by combining extracted features. Each neuron applies a weighted sum followed by a ReLU activation.

7. **Output Dense Layer (10 units, Softmax activation)** consists of 10 neurons—one for each class in the dataset. It outputs class probabilities using the softmax activation function.

#### Activation functions
- Relu Activation function is used in the hidden layers to introduce non-linearity and mitigate the vanishing gradient problem, enabling the network to learn complex relationships.
- Softmax output Activation function is used in the output layer to convert raw scores into a probability distribution. This ensures the probability outputs sum to 1, making it suitable for multi-class classification.

### Performance

Unfortunately, we can see below that while the accuracy in the training data is increasing rapidly as the epoch increases whereas the performance on the testing dataset plateaus at around epoch 4, indicating that the model is overfitting. A similiar problem is faced in the loss function as the validation dataset decreases before increasing again

![image](https://github.com/user-attachments/assets/b185e10f-5e4d-4b0c-adc9-65641b7ab05b)

### Managing overfitting

As there wasn't that many training samples, data augmentation was used so that each original training sample would make 2 more augmented training sample through rotating, flipping, changing the brightness and shifting the pixels. Including the augmented data in the model helps with the generalisation as the model accuracy plateaus at a higher accuracy than the un-augmented data, which is desired. However, both the difference between the training and validation data in the accuracy and loss plots still show signs of overfitting, despite the augmented data overfitting less than the un-augmented data. This reduced the model overfitting but more improvements can be made; which is a challenge as I don't have the GPU to run it.

![image](https://github.com/user-attachments/assets/48148ff8-7d92-4632-94bb-380110572a0e)

### Results
Here is a sample of the model prediciting some unseen images
![image](https://github.com/user-attachments/assets/69dca8cd-9ff4-4e9f-b1f4-5848cd5b703e)



