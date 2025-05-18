![image](https://github.com/user-attachments/assets/6439f465-795e-4bcc-a5dc-228046c61dae)# Image classification

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

### Baseline Performance

Unfortunately, we can see below that while the accuracy in the training data is increasing rapidly as the epoch increases whereas the performance on the testing dataset plateaus at around epoch 4, indicating that the model is overfitting. A similiar problem is faced in the loss function as the validation dataset decreases before increasing again.

![image](https://github.com/user-attachments/assets/b185e10f-5e4d-4b0c-adc9-65641b7ab05b)

### Managing overfitting

As there wasn't that many training samples, data augmentation was used so that each original training sample would make 2 more augmented training sample through rotating, flipping, changing the brightness and shifting the pixels. Including the augmented data in the model helps with the generalisation as the model accuracy plateaus at a higher accuracy than the un-augmented data, which is desired. We also see that adding dropouts and L2 regularisation helps with overfitting, enabling the model to be more robust.
![image](https://github.com/user-attachments/assets/5c90f425-6497-4ae9-9a1e-13572b96b31c)


### Results
After many tests with different hyper-parameter, a model with an accuracy of 82% was acheieved. Here is a sample of the model prediciting some unseen images

![image](https://github.com/user-attachments/assets/e0d956f4-f827-4954-9e53-79218d64cb88)




