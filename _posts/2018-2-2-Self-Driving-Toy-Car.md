---
layout: post
title: Self-Driving-Toy-Car
excerpt: How things works always fascinated me but when I was introduced to machine learning that I can teach machine like a baby, the first thing would be how to walk.
image: /images/bot.png
---
How things works always fascinated me but when I was introduced to machine learning that I can teach machine like a baby the first thing would 
be how to walk.So I started working on this project Self-driving toy car in a team of three.
# Car
Luckily to start with we already had bot which were given by the robotics club to first year student. All we have to do was to make modify that 
bot and make it suitable for the project.
<br>
The bot comprises of a motor driver IC L239D , a camera and a control webpage. The Bot is made to run on 4 different types of track , on
each lap the commands given to the bot , the image corresponding to that command are stored in a database.
The final car looks somthing like this
![](/images/bot.png)


# Autopilot 
The auto-pilot for the car is based on Nvidia's paper which predicts steering angle based on the image input.It uses Convolutional Neural Network artitecture.
We made a sight modification instead of the angle now this model predicts commands like 'w' for forward , 's' for backward etc.
The deep neural network itself takes input images (160 x 320 x 3). At the very beginning it contains normalization and cropping layers. This continues with 3
convolutional layers with 2x2 stride and 5x5 kernel. These are followed by additional 2 convolutional layers with no stride and 3x3 kernel. Convolution
layers are connected to three fully connected layers leading to an output control value. Non-linearity is introduced between all network layers with RELU
function. ADAM is used for our learning rates.
![](/images/neural.png)
# Loss function
For the model, the mean square loss function was used. This loss function is common for
regression problems. The MSE punishes large deviations harshly. This function is simple the mean
of the sum of the squared differences between the actual and predicted results.
# Results :
We trained above on around 32000 images collected on 4 different tracks 4 laps of each. We applied MSE for calculating efficiency which comes around 0.1640 for the most efficient trained model.
![](/images/2018-03-01-003307_1366x768_scrot.png)
