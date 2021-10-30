# Cats-and-Dogs-Image-Classification
Cats and dogs image Classification using Convolutional neural network, and deployed using flask.


you can download the data from here: https://www.kaggle.com/c/dogs-vs-cats/data


##Import libraires


We need to train a model first so we will check training data In the below code we are
iterating through all images in train folder and then we will split image name with delimiter “.”

we are going to use cv2 library to read our image into an array and also it will read as a grey scale image.
Declare your training array X and your target array y. Here X will be the array of pixels and y will be value 0 or 1 
indicating its a dog or cat Write convert function to map category “dog” or “cat” into 1 and 0

Create a function create_test_data which takes all training images into a loop. 
Converts into image array. Resize image into 80 X80. Append image into X array. Append category value into y array.

Now call the function, but also later convert X and y into numpy array We also have to reshape X with the below code.

If you see the values of X you can see a variety of values between 0- 255. Its because every pixel has different density of black and white. But with the wide range of values it becomes difficult for a training model to learn (sometimes memorize ).
How to resolve this And you guessed it right . You can normalize the data. 
We can use Keras normalize here also. But well, we already know all values are having range between 0-255 so we can just divide it by 255 and 
get all values scaled between 0 -1 That’s what we have done below. You can skip this step to see the difference between accuracy. Don’t believe everything I say. Experiment and see for yourself

Now we will fit our model with training data.
Epochs:- How many times our model will go through data
Batch size:- How much amount of data at once you want to pass through the model
validation_split :- How much amount of data (in this case its 20 %) you will need to check cross validation error


###Prediction and saving the model:

