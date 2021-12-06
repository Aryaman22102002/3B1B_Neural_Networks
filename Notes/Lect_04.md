# Back propagation calculus

## Chain rule

![Screenshot from 2021-12-06 10-14-06](https://user-images.githubusercontent.com/82901720/144788647-c479cee4-c19f-40b9-8550-eb8b2c8d57a4.png)

* Our aim is to find the change in cost function 'C' with respect to change in 'w'.
* The term 'del(C0)/del(w[L])' is the ratio of the nudge in the cost function to the nudge in w[L].
* This nudge to w[L] causes a nudge to z[L] which in turn causes a nudge to a[L] which directly influences the cost. 
* Therefore using the concept of chain rule in calculus, we can represent the sensitivity of 'Co' to small changes in 'w' as:
  
![20211206_012145](https://user-images.githubusercontent.com/82901720/144761575-669ba938-3dfa-4c7c-8013-c344914e62b4.jpg)

## What the derivatives mean ?

![20211206_012152](https://user-images.githubusercontent.com/82901720/144761573-8c08f12e-112e-46ea-ae9e-e8e05539e0d0.jpg)

* In the above image, in case of the last derivative, the amount of nudge to the weights of the last layer depends on how strong the previous neuron is. This is related to the idea, "The neurons that fire together wire together".
* This all was for a single training example. 
* For all training examples, we have to take average of the expression of the derivative of 'del(C0)/del(w[L])' we found over all training examples.

![Screenshot from 2021-12-06 01-42-52](https://user-images.githubusercontent.com/82901720/144762366-c1948937-0fb0-4047-94f2-aa57fe1fdda4.png)

* And this is one component of the gradient vector which is made up of derivatives of the cost function with all weights and biases present.

![Screenshot from 2021-12-05 22-33-38](https://user-images.githubusercontent.com/82901720/144788369-1ab32b70-1629-416f-8e00-b2d495ad74d1.png)

* The expression of the term 'del(C0)/del(b[L])' is as follows :
  
![20211206_012928](https://user-images.githubusercontent.com/82901720/144762034-14315a84-d66b-4bc8-9e73-d866bafce6b5.jpg)

* The expression of the term 'del(C0)/del(a[L-1])' is as follows :

![20211206_012931](https://user-images.githubusercontent.com/82901720/144762035-1e05c893-3c06-4697-8ae3-c0bd99b0a1af.jpg)

* Now we can keep iterating the chain rule concept backwards to see how sensitive the cost function is to previous weights and previous biases.

![Screenshot from 2021-12-05 22-40-20](https://user-images.githubusercontent.com/82901720/144762083-2a3463de-d182-44a1-83c5-f3e294213aa3.png)

## For multiple neurons per layer

* The above explanation was for single neuron. But for multiple neurons, the formulas aren't much different. There's only addition of a couple of extra indices to the terms.

![Screenshot from 2021-12-05 22-43-00](https://user-images.githubusercontent.com/82901720/144762155-8bfeff7d-0828-49bc-9f0e-c035637dfeae.png)

* The cost function now looks like :

![Screenshot from 2021-12-05 22-43-0011](https://user-images.githubusercontent.com/82901720/144762162-d7ce957e-39c0-4d98-bdb0-e75ae2c732a6.png)

* The 'del(C0)/del(w[L])' term also doesn't change much :

![20211206_012944](https://user-images.githubusercontent.com/82901720/144762040-5ec82c04-02d7-4f81-a235-3be260a2d07a.jpg)

* The 'del(C0)/del(a[L-1])' term changes quite a bit though :

![20211206_012947](https://user-images.githubusercontent.com/82901720/144762041-92d1dc04-5e55-4878-bb19-d0bfc61c76a8.jpg)

* Here the neuron influences the cost function through multiple different paths.

![Screenshot from 2021-12-05 22-50-39](https://user-images.githubusercontent.com/82901720/144762256-6f7ef5f3-8f23-48d5-914e-1fa4e26c08d6.png)

* Once we've understood this, we can repeat the process for each weight and bias available to us.