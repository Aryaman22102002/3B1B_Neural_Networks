# Back Propagation

## What is back propagation ?

![Screenshot from 2021-12-05 18-50-47](https://user-images.githubusercontent.com/82901720/144760451-70f61fb8-c42d-4867-ba14-0f09cfe55ca3.png)

* Suppose we want to classify the image as a '2'.
* Therefore, we want the third value in the above image to get nudged up while the other values to get nudged down.
* Also, the sizes of the nudges must be proportional from how far away their current value is from their desired value.
* There are three ways to increase the values.
    1. Increase the bias.
    2. Increase the weights.
    3. Increase the activations of the previous layers.

![Screenshot from 2021-12-05 18-56-46](https://user-images.githubusercontent.com/82901720/144760466-3780dc24-3747-48ef-b5a8-481cbfec2f8e.png)

* The change in the weights of the neurons of the previous layer having brighter connections with the final neuron representing '2' have more effect on the final neuron's value as compared to increasing the weights of the neurons of the previous layer having dimmer connections with the final neuron representing '2'.
* We can relate this to "Hebian Theory" which states "Neurons that fire together wire together". What this means is the biggest increasing of weights happen between the neurons which are the brightest and the neurons which you wish to be the brightest.
* So basically, to increase the activation of the neuron representing '2', we need to increase the activations of the neurons in the previous layer which have brighter connection with '2' and make it more brighter and we need to decrease the activations of the neurons in the previous layer which have dimmer connection with '2' and make them more dimmer.
* But the other neurons in the output layer need to also become more dimmer. They too, have their own desires of what should happen to the second last layer.
* So, in proportion to those weights and the desires of all neurons in the output layer, comes in the idea of propagating backwards.
* Adding the desired effects, we get a list of nudges that we want to happen to the second last layer. 

![Screenshot from 2021-12-05 19-08-21](https://user-images.githubusercontent.com/82901720/144760280-d2e7133a-dc30-49a9-80d1-877bb3848fef.png)

![Screenshot from 2021-12-05 19-10-08](https://user-images.githubusercontent.com/82901720/144760281-ba6b56b4-7b9d-4dd4-ac77-e2228e55feda.png)

* Repeating this process, we can propagate backwards to the third last layer, fourth last layer and so on.
* This was for one training example. We repeat this process for every training example and average out those nudges to weights and biases. This, loosely speaking, is the negative gradient of the cost function.

![Screenshot from 2021-12-05 19-11-21](https://user-images.githubusercontent.com/82901720/144760377-43a517eb-07be-4816-880a-ac2f76316f3f.png)

## Stochastic gradient descent

![Screenshot from 2021-12-05 19-18-50](https://user-images.githubusercontent.com/82901720/144760380-11f0d592-d0f0-4253-afdd-ae5422d5cba3.png)

* Computers take huge time to add up these desired nudges for each example. So we divide these training examples into small groups  and compute gradient descent on each group. 
* This speeds up our computation. It covers more distance while finding the local minima during gradient descent but it finds the local minima quickly. It takes quick steps instead of slow calculated steps.
* This is called stochastic gradient descent.

## Conclusion 

* Back propagation is the algorithm for determining how a single training example would like to nudge the weights and biases in terms of what relative proportions to those changes cause the most rapid decrease to the cost. 