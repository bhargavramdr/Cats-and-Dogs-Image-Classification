# Cats-and-Dogs-Image-Classification
Cats and dogs image Classification using Convolutional neural network, and deployed using flask.

Here's how it looks:

![Screenshot (192)](https://user-images.githubusercontent.com/72303641/139555207-6371bd77-66ff-4468-9670-c252dfbd946f.png)


you can download the data from here: https://www.kaggle.com/c/dogs-vs-cats/data


## Import libraires

![Screenshot (182)](https://user-images.githubusercontent.com/72303641/139521962-a1cee567-a414-42e9-a6ab-53e5013f92e8.png)


We need to train a model first so we will check training data In the below code we are
iterating through all images in train folder and then we will split image name with delimiter “.”. Because the name are like Dog.0. Dog.1, cat.0 etc.

![Screenshot (183)](https://user-images.githubusercontent.com/72303641/139521969-9f16f2d3-6384-4873-83c4-5f80cf6ba8cb.png)

we are going to use cv2 library to read our image into an array and also it will read as a grey scale image.
Declare your training array X and your target array y. Here X will be the array of pixels and y will be value 0 or 1 
indicating its a dog or cat Write convert function to map category “dog” or “cat” into 1 and 0.

![Screenshot (184)](https://user-images.githubusercontent.com/72303641/139521976-85631d33-9966-41ce-bb31-ab409e334dc5.png)

Create a function create_test_data which takes all training images into a loop. 
Converts into image array. Resize image into 80 X80. Append image into X array. Append category value into y array.


Now call the function, but also later convert X and y into numpy array We also have to reshape X with the below code.
If you see the values of X you can see a variety of values between 0- 255. Its because every pixel has different density of black and white. But with the wide range of values it becomes difficult for a training model to learn (sometimes memorize ).
How to resolve this And you guessed it right . You can normalize the data. 
We can use Keras normalize here also. But well, we already know all values are having range between 0-255 so we can just divide it by 255 and 
get all values scaled between 0 -1 That’s what we have done below. You can skip this step to see the difference between accuracy. Don’t believe everything I say. Experiment and see for yourself
![Screenshot (185)](https://user-images.githubusercontent.com/72303641/139521983-ebe85cef-47f7-4bca-ad00-c1c1bc6fb91d.png)

Now we will fit our model with training data.
![Screenshot (186)](https://user-images.githubusercontent.com/72303641/139522011-ecde1372-5132-4827-9dcc-3653d1382c9b.png)

Epochs:- How many times our model will go through data
Batch size:- How much amount of data at once you want to pass through the model
validation_split :- How much amount of data (in this case its 20 %) you will need to check cross validation error


### Prediction and saving the model:

![Screenshot (188)](https://user-images.githubusercontent.com/72303641/139522024-90578596-e7fe-44fe-849c-501dd0446f9e.png)

