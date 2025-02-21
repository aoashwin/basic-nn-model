# Developing a Neural Network Regression Model

## AIM

To develop a neural network regression model for the given dataset.

## THEORY

*A neural network with multiple hidden layers and multiple nodes in each hidden layer is known as a deep learning system or a deep neural network. Deep learning is the development of deep learning algorithms that can be used to train and predict output from complex data.The word “deep” in Deep Learning refers to the number of hidden layers i.e. depth of the neural network. Essentially, every neural network with more than three layers, that is, including the Input Layer and Output Layer can be considered a Deep Learning Model.TensorFlow, an open-source software library for machine learning, offers a robust framework for implementing neural network regression models.The Reluactivation function helps neural networks form deep learning models. Due to the vanishing gradient issues in different layers, you cannot use the hyperbolic tangent and sigmoid activation. You can overcome the gradient problems through the Relu activation function.


## Neural Network Model

![Screenshot 2022-08-29 084357](https://user-images.githubusercontent.com/75235601/187119912-ae203d33-bccd-412d-b52c-efbd9b27102f.jpg)



## DESIGN STEPS

### STEP 1:

Loading the dataset

### STEP 2:

Split the dataset into training and testing

### STEP 3:

Create MinMaxScalar objects ,fit the model and transform the data.

### STEP 4:

Build the Neural Network Model and compile the model.

### STEP 5:

Train the model with the training data.

### STEP 6:

Plot the performance plot

### STEP 7:

Evaluate the model with the testing data.
```
Developed by : Ao Ashwin 
reg no: 212220230005
```
## PROGRAM
```
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import  MinMaxScaler
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense
data=pd.read_csv("dl_ex01.csv")
data.head()
x=data[['Input']].values
x
y=data[['Output']].values
y
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.3,random_state=33)
Scaler=MinMaxScaler()
Scaler.fit(x_train)
Scaler.fit(x_test)
x_train1=Scaler.transform(x_train)
x_train1
x_train
AI_BRAIN=Sequential([
    Dense(9,activation='relu'),
    Dense(5,activation='relu'),
    Dense(1,activation='relu')
])
AI_BRAIN.compile(optimizer='rmsprop', loss='mse')
AI_BRAIN.fit(x_train1,y_train,epochs=4000)
loss_df=pd.DataFrame(AI_BRAIN.history.history)
loss_df.plot()
x_test1=Scaler.transform(x_test)
x_test1
AI_BRAIN.evaluate(x_test1,y_test)
x_n1=[[30]]
x_n1_1=Scaler.transform(x_n1)
AI_BRAIN.predict(x_n1_1)

```

## Dataset Information

![Screenshot 2022-08-29 092546](https://user-images.githubusercontent.com/75235601/187119976-699cfdb0-5bdb-498f-aaac-63323c2a0ddb.jpg)


## OUTPUT

### Training Loss Vs Iteration Plot

![Screenshot 2022-08-29 091921](https://user-images.githubusercontent.com/75235601/187120017-782004b5-8fae-4398-8183-cecfb3368490.jpg)


### Test Data Root Mean Squared Error

![Screenshot 2022-08-29 092014](https://user-images.githubusercontent.com/75235601/187120044-c52d8203-e3c3-45cf-bf46-e40735de3f6e.jpg)

### New Sample Data Prediction

![Screenshot 2022-08-29 091949](https://user-images.githubusercontent.com/75235601/187120072-b23b4512-d27b-477a-9d49-5a6ad387f80c.jpg)
![Screenshot 2022-08-29 091936](https://user-images.githubusercontent.com/75235601/187120075-df4484fd-2352-426b-a768-9b6db3672815.jpg)


## RESULT

Thus,the neural network regression model for the given dataset is developed.
