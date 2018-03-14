# Tensor Train Recurrent Neural Network 

[![Build Status](https://travis-ci.org/voxpelli/node-github-publish.svg?branch=master)](https://travis-ci.org/voxpelli/node-github-publish)
[![Coverage Status](https://coveralls.io/repos/voxpelli/node-github-publish/badge.svg)](https://coveralls.io/r/voxpelli/node-github-publish)
[![Dependency Status](https://gemnasium.com/voxpelli/node-github-publish.svg)](https://gemnasium.com/voxpelli/node-github-publish)

Clean code repo for tensor train recurrent neural network, implemented in Tensorflow.
See details in paper [Long-Term Forecasting with Tensor Train RNNs](https://arxiv.org/abs/1711.00073)

![](tlstm.png "Model Architecture for Tensor Train RNNs")

# Getting Started 

**install prerequisite**

* tensorflow >= r1.6
* Python >=3.0
* Jupyter >=4.1.1

**import module**

```python
from trnn import TensorLSTMCell
```

```python
from trnn_imply import tensor_rnn_with_feed_prev
```

## Classes

* **TensorLSTMCell(num\_units, num\_lags, rank\_vals)** – creates a `TensorTrainLSTM` object with `num_units` hidden nodes, `num_lags` time lags, with `rank_vals` is the list of values for tensor train decomposition rank

## Methods

* **tensor\_rnn\_with\_feed\_prev** – forward pass for a single `TensorTrainLSTM` cell, returns an `output` and a hidden state. 

## Running the test

A simple example of using `TensorTrainLSTM` by learning a `sim` function using a seq2seq model

* `jupyter notebook test_trnn.pynb`

## Directory

* **reader.py**
read the data into train/valid/test datasets, normalize the data if needed

* **model.py**
seq2seq model for sequence prediction

* **trnn.py**
tensor-train lstm cell and corresponding tensor train contraction

* **trnn_imply.py**
forward step in tensor-train rnn, feed previous predictions as input
