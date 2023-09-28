# MLChallenge
About the first task. Training a cnn model to recognize the traphic lights.

First we import the training and testing data with os library and crop the images based on the imformation from the annotations. We take 20% of the training data and keep it for evalutating our models.
Our first model only has two Convolutional Layers followed by two pooling layers, and two dence layers. The features, the learning rate and the bach size are quite randomly choosen and are changed to test diffrent features in the process.
This model only has 0.63 accuracy and the learning curves suggest that it needs improving, so we try Droping out 50% of our training data every epoch and we can see that the accuracy improoves radicaly and the learning curves show that the model learns more smoothly. 
After that we just make our model more complex to see how much the accuracy of the testing data impooves, while adjust the features accordingly to keep the learning curves more smooth. 
The channels (12,32,64,128)(32,64,128,256), and (64,128,256,512) we all tried in various changes of the model and at the end the best performance was with (32,64,128,256) number of channels.
At the end when we got the the model 5 with a really good performance at 90% accurasy but the curves of accuracy and loss suggested that the learning process isnt smooth and that it might be vunrable to diffrent parameters. ![image](https://github.com/stellagerantoni/MLChallenge/assets/105601416/114becb4-3947-4755-ae3c-e58785ef48e3)

