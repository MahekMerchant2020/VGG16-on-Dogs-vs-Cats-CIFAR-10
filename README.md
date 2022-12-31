# VGG16 on Dogs vs Cats & CIFAR-10

__[Kaggle | Dogs vs Cats](https://www.kaggle.com/c/dogs-vs-cats)__

The dog and cat images from the Kaggle dataset were divided into train, validation, and test folders in the following way.

![Dataset:](https://github.com/MahekMerchant2020/VGG16-on-Dogs-vs-Cats-CIFAR-10/blob/main/Dataset%20Structure.png)

Pre-processing: The images were pre-processed using the ImageDataGenerator() function in Keras and resized to 224 x 224 before being passed into the VGG16 model.

Training Strategy: Each layer (except the last softmax layer) from the downloaded VGG16 model was copied to the mini_model. The weights and trainable parameters of all the copied layers were frozen so that they do not get updated when we pass the dog and cat images to the model. Then, we added a new softmax layer with 2 output units to the mini_model. This softmax layer is the only trainable layer in the mini_model.

We compiled the mini_model by using the Adam optimiser with a learning rate of 0.0001, categorical_crossentropy as the loss function, and accuracy as our metric. The model was trained over 2 epochs.

Train Accuracy = 96.10%
Validation Accuracy = 97.20%

The predictions for the 500 unlabelled test images have been generated in "Mini Project Submission.csv".
We have fixed the random seeds for Numpy and TensorFlow to ensure reproducibility and generate the same results every time.

***
__[CIFAR-10 Dataset](https://www.cs.toronto.edu/~kriz/cifar.html)__
