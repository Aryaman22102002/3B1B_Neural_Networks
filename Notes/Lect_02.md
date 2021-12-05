# Gradient Descent, how neural networks learn?

## Training data and Testing data

* We first train the network with labeled data. We hope that the network will learn the patterns from this training data.
* After this, we give the network more labeled data in the form of testing data. This test data must be different from the training data and then we check the accuracy of the netwrok.

![Screenshot from 2021-11-25 00-38-00](https://user-images.githubusercontent.com/82901720/144759467-4818ffda-b4c7-4f12-b6ca-ca28831c8435.png)

## Cost Function

* We have assumed that every neuron in the first layer is connected to every neuron in the second layer and so on. The weights are like the strengths of these connections and the bias is an indication is whether the neuron tends to be active or inactive.

![Screenshot from 2021-11-25 00-42-40](https://user-images.githubusercontent.com/82901720/144759525-c6088328-acfa-4bb5-a6ef-32944bd7f0f1.png)

* The cost function is the summation of the squares of the differences between the actual activation outputs of the network(the output the network is giving) and the expected activation output(the output that should have been produced).
* The cost function(the sum) is small when the network confidently gives the correct output but large when the netwrok doesn't know what it's doing.
* So, we take the average cost of all the costs obtained for individual training examples.
* This tells us how good or bad the network is performing.
* The cost function takes all the weights and biases as inputs and gives a number as output(the cost) which tells us about the network's performance.
* This output number depends on the performance of the network on each and every piece of training example.
* Now we have to tell the network how to improve it's performance.
* For this we use calculus.

![Screenshot from 2021-11-25 00-54-16](https://user-images.githubusercontent.com/82901720/144759585-2e0434a8-bda0-4ced-8d9f-9f79c0816e5a.png)

* If the slope at a point is positive shift to the left and if the slope negative shift to the right.
* Doing this correctly over and over again, we eventually land at a minima(either local or global).
* When the slope is flattening out, our steps get smaller which saves us from overshooting.

## Gradient Descent 

* We should not ask about slopes. Instead we should as that which direction decreases most quickly.
* "Gradient" is the direction of steepest increase.

![Screenshot from 2021-11-25 01-01-23](https://user-images.githubusercontent.com/82901720/144759699-731157cc-9aa0-4d4f-9b88-9a04fb326021.png)

![20211206_010248](https://user-images.githubusercontent.com/82901720/144761108-3584064b-1296-4344-9512-a1172431deaa.jpg)

* Therefore, negative of that gradient will give the direction of steepest decrease.

![Screenshot from 2021-12-05 18-56-50](https://user-images.githubusercontent.com/82901720/144760006-2ddece03-209b-4b81-b35b-82b47c139b9b.png)

* This gradient descent changes our weights and biases so that we can achieve minimum of cost function quickly.
* A network is learning means its minimizing the cost function.
* The gradient vector tells us two things. Which value should increase or decrease and which value has more priority to be changed.

![Screenshot from 2021-11-25 01-06-52](https://user-images.githubusercontent.com/82901720/144759627-bce1d165-76b7-4791-8e23-7cff3b435b66.png)

## Analyzing the network

* In the last lecture, we hoped how each layer would behave. The 1st hidden layer would detect small edges and 2nd hidden layer would detect the major past that form a digit and the output layer would give the correct digit.
* Here, it actually doesn't happen like this. The 1st hidden layer looks random with a small loose pattern forming in the middle. This might be because the cost function has sat on any intermediate local minima instead of the global minima.

![Screenshot from 2021-12-06 00-30-11](https://user-images.githubusercontent.com/82901720/144760069-2a92eb0b-d3aa-4e44-be19-c0e7cf99714d.png)

* This was the method that was used in the past for image recognition.

![Screenshot from 2021-11-25 01-23-33](https://user-images.githubusercontent.com/82901720/144760153-0cc6b7e2-6f76-440b-b5be-10ed92b02151.png)