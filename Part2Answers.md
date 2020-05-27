* Name all the layers in the network, describe what they do.
1. 24x24 input layer, just propogates the pixel values to the next layer
2. Convolutional layer with 8 filters all applied on 5x5 grids centered at each pixel resulting in 8 24x24 images. Basically makes 8 different images where each pixel is a combination of the surrounding pixels from the original image.
3. Rectified Linear Unit activation on the previous convolutional layer.
4. Max pooling on 2x2 sections of each of the 8 images created in the previous layer. Takes max value of the four pixels in each grid.
5. Convolutional layer with 16 filters applied on 5x5x8 grids centered at each pixel. Combines the results of the 8 images generated previously in different ways to output 16 images.
6. Rectified Linear Unit activation on the previous convolutional layer.
7. Max pooling on 3x3 sections of each of th 16 images created in the previous layer. Takes max value of the 9 pixels in each grid. Outputs 16 4x4 images.
8. Fully connected layer with 256 input neurons and 10 output neurons representing each of the 10 prediction classes.
9. Softmax layer over the 10 prediction classes. Outputs probability that input image is each of the 10 classes.


* Experiment with the number and size of filters in each layer. Does it improve the accuracy?
Reducing filter size for the first convolutional layer seemed to increase accuracy slightly, but the effects of most changes were hard to perceive.


* Remove the pooling layers. Does it impact the accuracy?
Removing the pooling layers makes the network take longer to train but does not seem to impact the accuracy.


* Add one more conv layer. Does it help with accuracy?
Adding another convolutional layer does not seem to impact accuracy significantly.


* Increase the batch size. What impact does it have?
Increasing the batch size seems to reduce validation accuracy.

* What is the best accuracy you can achieve? Are you over 99%? 99.5%?
Letting the base model train for a few minutes achieves an accuracy of 99%, there is no fractional granularity given for the accuracy.~