WIP

# js-mind
Deep Learning Library Written in ES2015.

[API Documentation](https://shinout.github.io/js-mind/api)

## Features

  * Convolutional Neural Network
  * Softmax
  * L2 Regularization
  * Dropout

## TODO

  * Clustering
  * Lazy Loading
  * ReLU

## How To Use

```javascript
"use strict";

var jsmind = require("../dist");

var mnistLoader = jsmind.mnistLoader;
var trainingData = mnistLoader.loadTrainingDataWrapper();
var validationData = mnistLoader.loadValidationDataWrapper();
var testData = mnistLoader.loadTestDataWrapper();

var net = new jsmind.Network([
  new jsmind.layers.FullyConnectedLayer(784, 100, {pDropout: 0.5}),
  new jsmind.layers.FullyConnectedLayer(100, 100, {pDropout: 0.5}),
  new jsmind.layers.SoftmaxLayer(100, 10, {pDropout: 0.5})
]);

net.SGD(trainingData, 60, 10, 0.1, {
  validationData: validationData,
  testData: testData,
  lmbda: 0.1
});
```
