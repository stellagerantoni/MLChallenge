# MLChallenge

##First task. Training a cnn model to recognize the traphic lights.

First we import the training and testing data with os library and crop the images based on the imformation from the annotations. We take 20% of the training data and keep it for evalutating our models.

Our first model only has two Convolutional Layers followed by two pooling layers, and two dence layers. The features, the learning rate and the bach size are quite randomly choosen and are changed to test diffrent features in the process.
This model only has 0.63 accuracy and the learning curves suggest that it needs improving, so we try Droping out 50% of our training data every epoch and we can see that the accuracy improoves radicaly and the learning curves show that the model learns more smoothly. 
After that we just make our model more complex to see how much the accuracy of the testing data impooves, while adjust the features accordingly to keep the learning curves more smooth. 
The channels (12,32,64,128)(32,64,128,256), and (64,128,256,512) we all tried in various changes of the model and at the end the best performance was with (32,64,128,256) number of channels.

At the end when we got the the model 5 with a really good performance at 90% accurasy but the curves of accuracy and loss suggested that the learning process isnt smooth and that it might be vunrable to diffrent parameters.

![image](https://github.com/stellagerantoni/MLChallenge/assets/105601416/114becb4-3947-4755-ae3c-e58785ef48e3)

So we try diffrent learning rates, channels and bach sizes to try and smoothen out the curves (without hurting the accuracy of the model on the testing data.)

learning rates tried: (0,01, 0,001, 0,0001 , 0,00001)

Best lerning rate: 0,001

bach sizes: (32, 64, 128, and 256) 

best bach size: 128

By updating these parameters we get: Classifier trained, with testing accuracy 0.9008792610751826.

And the learning curves smoothen out a bit.

![image](https://github.com/stellagerantoni/MLChallenge/assets/105601416/d78ba136-ca0d-4825-a7a2-4c590144fdff)

##Adding noise to the model.

The model performance drops by more than 15% when we add noise to the test set, wich is something to be expected. 


##Task 2: Pinhole Cameras

We first need to calculate where the points fall in the coordinate system placted in the center of our image plane, and are calculated with these two equations:

  y1 = -f*p_x/p_z
  y2 = -f*p_y/p_z

After we have our new point we need to check if they fall in the boundaries of our image plane wich are 

-h/2, h/2 and -w/2, w/2

For the sphere we only need one point at the image plane to calculate the distance from the camera.

distance = absolute(z) = -f * x /(r*s)


