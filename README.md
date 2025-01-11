# Fashion_MNIST
This project was developed in the "Introduction to Machine Learning" course. The goal was to design and implement a simple Convolutional Neural Network (CNN) model to classify images in the Fashion MNIST dataset. The project includes visualizing the CNN architecture better to understand the structure and functionality of its layers.

## Layer-by-Layer Explanation

### Convolutional Layer 1
- **Type**: Conv2D  
- **Parameters**:  
  - 32 filters  
  - Kernel size: (3, 3)  
  - Activation: ReLU  
  - Input shape: (28, 28, 1) (grayscale images of size 28x28)  
- **Function**:  
  Extracts low-level features such as edges and textures from the input image. Each filter slides over the input to apply a convolution operation, learning distinct spatial patterns.

### Max Pooling Layer 1
- **Type**: MaxPooling2D  
- **Parameters**:  
  - Pool size: (2, 2)  
- **Function**:  
  Reduces the spatial dimensions of the feature maps by half, retaining the most important features. This downsizing reduces computational complexity and helps prevent overfitting.

### Dropout Layer 1
- **Type**: Dropout  
- **Parameters**:  
  - Dropout rate: 30% (randomly drops 30% of neurons)  
- **Function**:  
  Helps prevent overfitting by deactivating random neurons during training, ensuring the model does not rely too heavily on specific features.

### Convolutional Layer 2
- **Type**: Conv2D  
- **Parameters**:  
  - 64 filters  
  - Kernel size: (3, 3)  
  - Activation: ReLU  
- **Function**:  
  Learns more complex patterns, such as shapes and textures, from the output of the first convolutional block.

### Max Pooling Layer 2
- **Type**: MaxPooling2D  
- **Parameters**:  
  - Pool size: (2, 2)  
- **Function**:  
  Further, it reduces the spatial dimensions of the feature maps and consolidates learned features, aiding in reducing overfitting and computational demands.

### Dropout Layer 2
- **Type**: Dropout  
- **Parameters**:  
  - Dropout rate: 30%  
- **Function**:  
  Like Dropout Layer 1, this layer reduces overfitting, particularly as the network progresses to deeper layers.

### Flatten Layer
- **Type**: Flatten  
- **Function**:  
  Converts the 2D feature maps from the convolutional and pooling layers into a 1D vector. This transformation prepares the data for the fully connected layers.

### Fully Connected Layer 1
- **Type**: Dense  
- **Parameters**:  
  - 128 neurons  
  - Activation: ReLU  
- **Function**:  
  Acts as a classifier by learning complex interactions between features in the flattened data. The ReLU activation introduces non-linearity, allowing the model to learn more sophisticated patterns.

### Dropout Layer 3
- **Type**: Dropout  
- **Parameters**:  
  - Dropout rate: 50%  
- **Function**:  
  A higher dropout rate at this stage helps significantly reduce overfitting in the dense layers, where parameters are most abundant.

### Output Layer
- **Type**: Dense  
- **Parameters**:  
  - 10 neurons  
  - Activation: Softmax  
- **Function**:  
  Produces probabilities for each of the 10 classes. The softmax activation ensures that the output forms a valid probability distribution, summing to 1.
