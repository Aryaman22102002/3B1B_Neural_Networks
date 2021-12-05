# What is a neural network ?

We will use a neural network which can recognize digits from 0 to 9 as an example. It has 1 input layer, 2 hidden layers and 1 output layer.

## Neurons

* Neural networks are inspired by our brain.
* Neuron is a thing that holds a number, usually between 0 and 1.

![20211206_010038](https://user-images.githubusercontent.com/82901720/144761086-e09bcdeb-51df-4c41-b6b7-a47c382ffaa2.jpg)

![Screenshot from 2021-11-24 16-05-16](https://user-images.githubusercontent.com/82901720/144759265-274895e2-90f8-43d9-ab95-5f5fa3ec37cc.png)

* In the image above, each neuron holds grayscale value which moves towards 0 if the neuron holds black pixels and moves towards 1 if the neuron holds white pixels.
* The number inside the neuron is it's activation.
* Here, we can think of it as each neuron is lit up if it's activation is a high number.

## Layers

![Screenshot from 2021-11-24 19-03-34](https://user-images.githubusercontent.com/82901720/144758902-142a1620-9aeb-4a27-b9cc-036d5d9411d4.png)

* All of the 784 neurons in the above image form the first layer of our network.
* The last layer consists of 10 neurons numbered from 0 to 9 where each neuron's activation tells us how much the system thinks the given image corresponds with the number that the neuron is representing.
* The layers in the middle are called hidden layers.
* If we input an image lighting all the neurons in the first layer, that patter of activation depending upon each pixels brightness fires other neurons and causes some patter in the next layer which in turn causes another pattern in the next layer and so on until finally in the pattern obtained in the output layer, the number corresponding to the brightest neuron is the network's choice of which digit does the input layer represent.

#### What do the hidden layers do?

* Each digit from 0 to 9 can be broken down into some shapes/loops.

![Screenshot from 2021-11-24 19-33-59](https://user-images.githubusercontent.com/82901720/144761316-8c98cdac-5bc7-4b9c-8b60-35d3ca744cf1.png)

![Screenshot from 2021-11-24 19-37-26](https://user-images.githubusercontent.com/82901720/144758930-06848ca9-a657-4cc6-9d4c-9b4c52ebd26d.png)

* When we enter a number say 9, we hope that any of the loop patterns in the second last layer(3rd layer here) lights up whether it my be the loop from 9 or 8 or any other digit which has a loop as a part of it.
* Going from the second last layer to the output layer(4th layer here) just requires which combination of sub-components(i.e. shapes) correspond to which digit.
* Now each small loop or line is also composed of smaller curves or lines. 

 ![Screenshot from 2021-12-06 00-04-38](https://user-images.githubusercontent.com/82901720/144759094-18c067a0-4155-4714-86b5-0186d30a2e61.png)

* So here the 2nd layer of the network will correspond with the little edges or curves.
* So for example, when we take 9 as input in the first layer, the neurons in the second layer associated with all the small edges and curves that make up the input image (9 here) light up.
* Then all the neurons corresponding to the the loop and the straight line of 9 light up. 
* Finally in the 4th layer, neuron representing digit 9 lights up.
* This process is based on our assumption that the network will work like this.

![Screenshot from 2021-11-24 19-48-32](https://user-images.githubusercontent.com/82901720/144761346-f190a967-bf15-455d-8651-e9f41f3547d3.png)

## How activations in one layer might determine the activations in the next?

* There has to be a mechanism which converts pixels into edges, edges into patterns and patterns into the number.

![Screenshot from 2021-11-24 21-58-41](https://user-images.githubusercontent.com/82901720/144759303-1e6830be-f395-4e90-b2c5-bab5141090bb.png)

* Suppose we want to detect an edge in the white region shown above.
* What we do is we assign weights 'w' to each neuron in each layer.
* Then we take activation 'a' of each neuron in each layer and calculate the weighted sum.(w*a)
* The neurons corresponding to the region of interest will be given positive weights(shown in green) and for edge detection the thin region surrounding the region of interest is given negative weights which are shown in red. 
* The rest of the area is given zero weight value(the non coloured region).
  
![Screenshot from 2021-11-24 22-02-06](https://user-images.githubusercontent.com/82901720/144759299-ea6a3ca0-fab8-43c8-9811-f98126fcb245.png)

## Weights and biases

#### Weights

* When we calculate a weighted sum as shown above, the output can be any real number.
* But for this network we want the activations to be between 0 and 1.
* Therefore we have to map the number line between 0 and 1.
* For this we use functions. One such example is the sigmoid example/logistic curve.
* The sigmoid function's output is always between 0 and 1 as shown in the figure.

![20211206_010111](https://user-images.githubusercontent.com/82901720/144761091-b7ef18f2-11cf-4d1c-90e5-dddcd177164f.jpg)

* So the activation of a neuron is a measure of how positive the relevant weighted sum is.

#### Bias 

* What if we want to neuron to light up(i.e. be active) when the weighted sum is greater than 10 instead of greater than 0?
* Therefore, we need to add a bias for it be inactive.

![20211206_010211](https://user-images.githubusercontent.com/82901720/144761096-70bff045-233b-4e3f-b242-d1c2fcb286c4.jpg)

* So the weights tell us what pixel pattern the neuron is picking up upon and the bias tells us how high the weighted sum needs to be before the neuron becomes active.
* In this way, we calculate for each neuron in every layer throughout the network.

## Notations in linear algebra

* To write so many relations in a compact manner, we use vectors in linear algebra.
  
![20211206_010225](https://user-images.githubusercontent.com/82901720/144761099-57657c2f-b637-4011-a413-5acf14eb76ff.jpg)

![20211206_010631](https://user-images.githubusercontent.com/82901720/144761102-2e9f845d-d9ec-4f35-8944-102fd1345d2b.jpg)

## Miscellaneous 

* So neurons can be thought of as functions which take outputs of the neurons from the previous layer as inputs and give a number between 0 and 1 as output.
* Instead of sigmoid function, nowadays we use the Relu(Rectified Linear Unit) function.

![20211206_010241](https://user-images.githubusercontent.com/82901720/144761106-31149458-c131-442e-a338-6718f7a49c2d.jpg)

* This function is more effective than sigmoid function because Relu function has a steep slope(1) for all positive inputs and this helps our network to learn faster as compared to sigmoid function which has places where the slope is 0 which slows the process of gradient descent and thus slows the process of learning.