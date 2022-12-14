# Machine Learning with Python

## Introduction

There are 2 types of programming methods

1. Classical programming
2. Machine learning programming

Classical programming takes data and rules as inputs and outputs answers. 

Machine learning programming takes data and answers as input and outputs rules

## Feature and Label

Feature is the input data. Label is the output which is what we’re trying to predict

## AI and Neural Network

Machine learning is a subset of artificial intelligence (AI). Neural networks (NN) are a part of machine learning (ML). 

Neural network is a form of machine learning that uses a layered representation of data

## TensorFlow

TensorFlow represents tensors as n-dimensional arrays. Tensor is a generalization of vectors and matrices to potentially higher dimensions. Vectors can have any number of dimensions

- 1d is a number (scalar)
- 2d is a 2d graph with x and y numbers
- 3d is a graph with x, y and z numbers
- 4d is image data or video data

TensorFlow programs work by building a graph of Tensor objects that details how tensors are related

Tensors have a data type and a shape

- Data types: float32, int32, string, etc
- Shape describes the dimension of data

## Creating a Rank 0 Tensor

```jsx
import tensorflow as tf

string = tf.Variable('this is a string', tf.string)
number = tf.Variable(324, tf.int16)
floating = tf.Variable(3.567, tf.float64)
```

Here, first argument is the object and 2nd argument is the data type. These 3 tensors one dimensional. They are also called scalars (rank 0 tensors)

Rank is the number of dimensions involved in the tensor

## Creating High Rank Tensor

```jsx
rank1_tensor = tf.Variable([‘Test’], tf.string)
rank2_tensor = tf.Variable([[‘Test’, ‘ok’], [‘Test’, ‘Yes’]], tf.string)
```

Here, rank2_tensor has a list inside a list (nested list). This tensor is a matrix

## Finding the Rank of a Tensor

```jsx
tf.rank(rank2_tensor)
tf.rank(rank1_tensor)
```

Here, rank of rank2_tensor is 2 while rank of rank1_tensor is 1

## Finding the Shape of a Tensor

```jsx
rank2_tensor.shape
```

Here, shape of rank2_tensor is (2, 2). Here, we have 2 numbers because this is a rank 2 tensor.

This means there are 2 items inside and each of those items also have 2 items inside

(3, 4, 2) means there are 3 items and they have 4 items each which has 2 items each. Here, we have 3 numbers because this is a rank 3 tensor.

Items of same level should have same number of items each

Shape of a rank 0 tensor is ()

## Changing Shape of a Tensor (Reshaping)

```jsx
tensor1 = tf.ones([1, 2, 3])
tensor2 = tf.reshape(tensor1, [2, 3, 1])
tensor3 = tf.reshape(tensor2, [3, -1])
```

tf.ones() creates a shape [1, 2, 3] tensor full of ones

[1, 2, 3] means 1 list has 2 lists and those 2 lists have 3 lists each

Both former and reshaped tensors should have same number of elements

In the last line, -1 is used to let tensor calculate the size of that place which will result in (3, 2) because 3*2 is 6

## Types of Tensors

Most common types,

- Variable
- Constant
- Placeholder
- SparseTensor

All these tensors are immutable (can’t change the value) except variables

## Evaluating Tensors

Evaluating tensor means getting its value. Sometimes, we have to run a ‘session’ to evaluate a tensor. 

This is how it’s done

```jsx
with tf.Session() as sess:
    tensor1.eval()
```

.Session() creates a session using default graph 

Here, we evaulate tensor1 variable that’s stored in default graph which holds all operations not specified to any other graph

## TensorFlow Core Learning Algorithms

4 main algorithms will be discussed here

- Linear regression
- Classification
- Clustering
- Hidden markov models
