# Image_classification

### CNN Architecture

For this application I went with this model architecture:

1. **Convolutional layer with 5x5 pixels kernels and 32 filters**: applies 32 filters, where each filter recognises a specific features such as curves, edges or texture from the input and each filters creates a feature map highlighting features where the pattern is present. A 5x5 kernel helps with capturing more complex patterns and higher number of filters allow for more diverse feature extraction.
2. **Max pooling by a factor of 2**: downsamples the dimensions of the features map by half while still keeping the important features to help with computation speeds.
3. **Convolutional layer with 3x3 pixels kernels and 64 filters**: applies 64 filters, as higher filters allow for more diverse feature extraction. A smaller 3x3 kernels help capture more fine-grained features/patterns at the local level.
4. **Max pooling by a factor of 2**: downsamples the dimensions of the features map by half while still keeping the important features to help with computation speeds.
5. **Flatten**: Converts the features-map into a 1D vector so that the results from the convolutional layers can be compatible with the dense layer after
6. **Dense layer with 64 units**: create a fully connect layer containing 64 neurons, where each neuron takes weighted sum of it’s input and adds a bias to it passing the result to the Relu function
7. **Dense layer with 10 units**: creates a fully connected layer with 10 neurons taking inputs from layer 6 and perform classification
