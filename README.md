## RadarNet
Deep Learning Convolutional-Deconvolutional Framework to short-term Climate Forecasting


## Introduction
RadarNet implements of a Convolutional-Deconvolutional Neural Network (CDNN) to short-term precipitation forecasting. Also provides an estimation of the advection field by using optical flow. 

RadarNet is intended to rapid implementation and testing of Deep Learning architectures to Climate Research. Please refer to documentation for more information.


## Code style
PEP 8 -- Style Guide for Python Code.


## Screenshot
Example of a real 30-min precipitation sequence:

![alt text](/Images/real_sequence_example.png)


Sequence generated by the model:

![alt text](/Images/predicted_sequence.png)


Estimated optical flow:

![alt text](/Images/optical_flow.png)


## Tech/framework used

<b>Built using:</b>
- [PyTorch](http://pytorch.org)


## Features

1. <strong>Training:</strong> Model training with built-in database.
2. <strong>Visualization:</strong> Real time visualization of training losses.
3. <strong>Forecasting:</strong> Built in forecasting routine to produce 50 min forecast sequences.


## Installation
<strong>Clone repository:</strong>
`git clone https://github.com/nabimaru/RadarNet`


## Usage
1. ### Training:
To train a model with your own data use the `train.py` script. The following command line arguments can be passed:

<strong>-arch:</strong> Neural network architecture to be used. Use 'scd' to train the default Convolution Deconvolution architecture.

<strong>-b:</strong> Batch size.

<strong>-e:</strong> Number of epochs.

<strong>-op:</strong> Optimizer, insert 'Adam' to use the Adam optimizer, 'SGD' to stochastic gradient descent.

<strong>Example of code</strong> : `python train.py -arch scd -b 512 -e 300 -op Adam`

<strong>Output</strong>:

- Model's weights are saved in a file inside the `Models/` folder.
- Visdom visualization server shows the progress of the loss real-time for every epoch

2. ### Visualization:
To generate and visualize predictions with your model, run the `viz.py` script with the following commands:

<strong>-arch:</strong> Neural network architecture to be used. Use 'scd' when using Soft Convolution Deconvolution architecture.

<strong>-s:</strong> Starting sequence index from data provided *default=0*.

<strong>-c:</strong> Number of maps to predict *5-minutes forecasting each*.

<strong>-seq:</strong> Type of sequence. Set to 1 to visualize a continuous map sequence with autoregression, 0 to indivudual forecasting for every input.

<strong>Example:</strong> `python viz.py -arch scd -s 600 -c 7 -seq 1`

<strong>Output:</strong>  
- Visdom server window shows the both target and predicted maps starting from example '-s' untill '-s' + '-c'.

## Status
RadarNet is currently under developement.

## Contribute
RadarNet is totally free and open for everyone to use, please feel free to contribute!


