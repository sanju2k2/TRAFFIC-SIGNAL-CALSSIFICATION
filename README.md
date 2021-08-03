# TRAFFIC-SIGNAL-CALSSIFICATION
### A Model that's able to predict many traffic signs ( say speed limit-20,30,.. & Stop, turn left,right,...& many more)
### There are 43 different traffic signs(i.e., features) that were used for prediction and some were listed above.
# How was Model built?
### 1) Firstly, I've imported all 43 classes(i.e., traffic signs(features)) that have the training data(i.e., Images) in it
### 2) Then, I've Done the Train-Test split and then Under Training data Train-Validation split to Validate the data & also check their shapes
### 3) Then, Got the labels(i.e., target) and then few pieces of code to know what images we have in the features data
### 4) Then, performed Pre-processing( i.e., COnverting BGR to Grayscale, and equalizing the pixel values...)
### 5) And then appplying those Pre-processings to the features(i.e., Training, test and validation images) and randomly checking the images to see how they look
### 6) Then, Reshaping the features such that they are ensured to be 1 colored channel ( .reshape( , , , 1))
### 7) Then, Applying Image Augmentation techniques to ensure that even though if some images are Rotated or shifted (width& height) or sheared... , they could be captured by our model.
### 8) As CNN cannot capture if images are sheared or rotated or width,height shifted and so on.
### 9) Now, we've Got to fit the training data with the ImageDataGenerator(i.e., Image Augmentation ) and then flow and get batches and via which we get Augmented images.
### 10) Now, a piece of code to see how our images look after Augmentation.
### 11) Now, we've to apply ONE-HOT ENCODING on the TARGET column( i.e., on Train, test as well as validation data)
### 12) Now, we've to import all the necessary layers, models and optimizers.
## 13) Firstly, We SPECIFY OUR ARCHITECTURE (i.e., We specify our model(i.e., Sequential), then the Layers( Dense,Conv2D,MaxPooling2D,Flatten and Dropout desirably) and then the number of layers inside each layer we specify and the Activation Functions(i.e., Softmax (on Last layer), Relu (on rest layers)) 
### => MODEL: SEQUENTIAL ( The sequential API allows you to create models layer-by-layer  where each layer has exactly one input tensor and one output tensor. Each layer has weights that correspond to the layer followed by it. We use the 'add()' function to add layers to our model. It is limited that it does not allow you to create models that share layers or have multiple inputs or outputs.)
### => LAYERS : 1) DENSE ( Each neuron in a layer receives an input from all the neurons present in the previous layer ,thus, they're densely connected. In other words, the dense layer is a fully connected layer, meaning all the neurons in a layer are connected to those in the next layer. The output generated by the dense layer is an 'm' dimensional vector. Thus, dense layer can also be  basically used for changing the dimensions of the vector ) 
### 2) FLATTEN ( Flattening is converting the data into a 1-dimensional array for inputting it to the next layer. We flatten the output of the convolutional layers to create a single long feature vector. And it is connected to the final classification model, which is called a fully-connected layer. )
### 3) CONV2D ( Convolutional layers are the major building blocks used in convolutional neural networks. A convolution is the simple application of a filter to an input that results in an activation. The result is highly specific features that can be detected anywhere on input images. In simple terms Its used to detect an edge.)
### 4) MAXPOOLING2D ( Max pooling operation for 2D spatial data downsamples the input along its spatial dimensions (height and width) by taking the maximum value over an input window (of size defined by pool_size ) for each channel of the input. The window is shifted by strides along each dimension. Simply it reduces the size of the Convolution layer.)
### 5) DROPOUT ( Dropout is a technique used to prevent a model from overfitting. Dropout works by randomly setting the outgoing edges of hidden units (neurons that make up hidden layers) to 0 at each update of the training phase. Dropout may be implemented on any or all hidden layers in the network as well as the visible or input layer. It is not used on the output layer. The term “dropout” refers to dropping out units (hidden and visible) in a neural network. Dropout is not used after training when making a prediction with the fit network. The main advantage of this method is that it prevents all neurons in a layer from synchronously optimizing their weights. This adaptation, made in random groups, prevents all the neurons from converging to the same goal, thus decorrelating the weights.)
### => ACTIVATION FUNCTION : 1) SOFTMAX ( Softmax turn logits (numeric output of the last linear layer of a multi-class classification neural network) into probabilities by take the exponents of each output and then normalize each number by the sum of those exponents so the entire output vector adds up to one(i.e., e^z/sigma(e^z) sigma = summation of all values) ==> all probabilities should add up to one.) 
### 2) RELU ( The Rectified Linear Unit is the most commonly used activation function in deep learning models. The function returns 0 if it receives any negative input, but for any positive value x it returns that value back. But the ReLU function works great in most applications, and it is very widely used as a result.)
## 14) 
