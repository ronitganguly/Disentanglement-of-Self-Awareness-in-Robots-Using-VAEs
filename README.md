# Disentanglement-of-Self-Awareness-in-Robots-Using-VAEs
This is a brief description on the University project that I worked on as a part of my Master's thesis


Please ask for the full research thesis to understand about the project.

## Context
Representation of the world of robot comes from the theory behind world models and Variational  Auto-Encoders. World models paper discusses how humans store a compressed representation of  their respective worlds in their minds which allows them to make predictions of the future and take  necessary actions. Similar objectives may be achieved in machines using generative neural  networks, such as Variational Auto-Encoders (VAEs). The VAEs are special Auto-Encoders which use a  KL divergence regularizer along with the reconstruction error. This regularizer forces the high  dimensional latent space to become regular, and a sufficiently smooth latent space allows for  disentanglement of latent dimensions. 
If the VAE is properly trained, the disentanglement of latent dimensions here essentially means that  each of these dimensions represents a specific feature about the input data, and varying them will  not affect the other. For example, one of the latent dimensions may learn to control colors,  while the other one can learn the arms of the Baxter robot as shown in the pictures below: 
  
![plot](./images/Capture1.png)

In this project, the focus is to train VAEs to disentangle the self of the robot from the environment.  Secondly, detect the dimensions which learn the arms as shown in the images above, and evaluate  the hypotheses that will be stated in the upcoming sections. Moreover, proper disentanglement will  enable the robot to imagine its self in new environments. Concretely, this means the robot attains  some self-awareness using a VAE and imagines itself in new surroundings.  
Imagining itself in new surroundings increases the productivity of the robot. The paper in discusses Level 1 self-awareness where a robot can distinguish itself spatially from its surrounding. This project also builds on that idea by using a generative network(VAE) instead of a deterministic network. 

## Objective: 

The overall objective of this project is to design VAEs which can disentangle the self-awareness of  the robot from the environment. To do so, this project evaluates two hypotheses: 

Hypothesis 1: 

Variational Auto-Encoders provide the means for modeling the self via the latent space and  encapsulates and disentangles the robot's representation of self-awareness. 
In other words, VAEs encode information into the latent space. If the information about the self of  the robot is encoded into this compressed high-dimensional and smooth latent space using the VAE,  then along with learning its self, the robot should also be able to disentangle its self from the rest of  the environment and imagine itself in new surroundings.  

Hypothesis 2: 

The input images should have distinctive and invariant visual features that allow the Variational  Auto-Encoders to disentangle them. 

### Model:

INSERT IMAGES HERE

###  Input Data For VAEs: 
Types of Data (required for the first hypothesis):  
The project is using two kinds of input data required to train the Variational Auto-Encoders, and  they are as follows: 
∙ RGB Images of resolution 128 X 128 pixels to train the Image VAE. 
∙ Vectors of proprioception data of the arms of the robot to train the proprioception VAE. 
The input data, which are the simulations of the Baxter robot in different environments, have been  provided by the supervisor of this project. There are a total of 32,303 images and the same number  of corresponding proprioception data. 
The raw input images are of size 640 X 480 pixels. However, the size is cropped to 128 X 128 pixels  which are suitable for training the Image VAE. Now, there are two kinds of these images: 
∙ Images with the arms of the Baxter robot are visible in the environment( cropped to  128X128 pixels): 

INSERT IMAGES HERE

∙ There are a total of 22,218 images with the arm of the Baxter robot visible in the  environment. 
∙ Images without the arms visible in the environment ( cropped to 128X128 pixels):

INSERT IMAGES HERE

∙ There are a total of 10,218 images of the environment where the arms are not visible. ∙ The environment images are essentially the images where the arms are not in the front or  they are waving in the background.  

The proprioception data is provided in a table format containing three features: Position, Velocity,  and Effort. All of these three proprioception features provide crucial information about the location  of the arms of the robot, the velocity with which the arms are swinging and the effort required.

### Types of Data (required for the second hypothesis):  

The experiment that has been conducted for supporting the second hypothesis uses a total of 100  randomly chosen unique environment images from the entire collection used in the first hypothesis  experiments. Additionally, 50 of these images have been edited by introducing a specific kind of arm of the Baxter robot:

INSERT IMAGES HERE

This specific arm has been cropped from its original image and put into those 50 different  backgrounds using online software, and there is no compulsion to use this kind of arm. Moreover,  each of these 50 images with the arm has been multiplied 50 times creating 2,500 total images with  the arm in them. On the other hand, the rest of the 50 unique environment images have been  multiplied 300 times producing 15,000 environment images. The idea is to let the Image VAE know  that the arm of the robot is only in 2,500 images with 50 different backgrounds. This should help the  Image VAE to learn that the arm can be disentangled from the variable background and reproduced  in the rest of the 50 different environment images.  

## Some results:

Insert IMAGES HERE
