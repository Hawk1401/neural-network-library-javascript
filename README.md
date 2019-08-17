"# neural-network-library-javascript"

- [Neural Network](#neural-network)
- [Download and Installation](#download-and-installation)
- [Creating a Neural Network with the constructor function](#creating-a-neural-network-with-the-constructor-function)
- [Feed forward](#feed-forward)
- [Training](#training)
- [copy](#copy)
- [mutate](#mutate)
- [reset](#reset)
- [SaveBrain](#savebrain)
- [Load Json](#load-json)
- [set Learning Rate](#set-learning-rate)
- [get Learning Rate](#get-learning-rate)
  


# Neural Network

This is a basic set up for a 2D neural Network. This Neural Network supports the genetic algorithm and supervised learning. The main use for this are web games or simple image recognition. 

# Download and Installation

 -Clone the repo: git clone `https://github.com/Hawk1401/neural-network-library-javascript.git`


# Creating a Neural Network with the constructor function

```javascript
let NN;

nn = new NeuralNetwork(5, 7, 7, 4, 0.01)
// new NeuralNetwork(inputLayer, hiddenLayer1, hiddenLayer2, outputLayer, learningRate)
```
This code will give us a Neural Network with this structure. 

![nn](https://miro.medium.com/proxy/1*DW0Ccmj1hZ0OvSXi7Kz5MQ.jpeg)

# Feed forward

```javascript
let nn;
let inputArray = [0.3, 0, 0.8, 1, 0.11]; 

nn = new NeuralNetwork(5, 7, 7, 4, 0.01)



let target = nn.feedForward(inputArray);

switch (target) {
    case 0:
        brake();
        break
    case 1:
        accelerate();
        break
    case 2:
        turnLeft();
        break
    case 3:
        turnRight();
        break
    case 4:
        driveBackwards();
        break
}
```

feedForward() needs an input array with the same length as it has input neurons. It will return the index of the highest output array.

# Training

```javascript

let nn;
let expectedArray = [0, 0, 1, 0];
let inputArray = [0.3, 0, 0.8, 1, 0.11];

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);

nn.training(inputArray, expectedArray);
```

The training() function will use supervised learning to adjust the connections. for this it needs 2 arguments, the first one is the inputArray like in feedForward() the second is an array with the label data.
# copy

```javascript
let nn;

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);

let brain = nn.copy();
```

The copy function will return a copy of the Neural Network.


# mutate

```javascript

let nn;

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);
nn.mutate();
```
The mutate() function will randomly change each connection by the probability of the learning rate. (1 = 100%)
# reset

```javascript
let nn;

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);
nn.reSet();
``` 
The reSet function will reset all connections randomly.

# SaveBrain

```javascript
let nn;
let expectedArray = [0, 0, 1, 0];
let inputArray = [0.3, 0, 0.8, 1, 0.11];

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);

nn.training(inputArray, expectedArray);
nn.saveBrain();
```

The saveBrain function will save the whole Neural Network as a json file.

# Load Json


```javascript
let nn;
let myJson = //load the json file

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);
nn.loadNewConnections(myJson);
``` 

The loadNewConnections() function will load a saved Neural Network 

# set Learning Rate

```javascript
let nn;

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);

nn.setLearningRate(0.001);
//Learning Rate is now 0.001
``` 

# get Learning Rate

```javascript
let nn;

nn = new NeuralNetwork(5, 7, 7, 4, 0.01);

let lr = nn.getLearningRate(0.001);
//return the Learning Rate
```


