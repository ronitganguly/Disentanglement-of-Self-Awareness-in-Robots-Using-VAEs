# Disentanglement-of-Self-Awareness-in-Robots-Using-VAEs
This is a brief description on the University project that I worked on as a part of my Master's thesis


Please ask for the full research thesis to understand about the project.

## Context
Representation of the world of robot comes from the theory behind world models[1] and Variational  Auto-Encoders[2]. World models paper discusses how humans store a compressed representation of  their respective worlds in their minds which allows them to make predictions of the future and take  necessary actions[1]. Similar objectives may be achieved in machines using generative neural  networks, such as Variational Auto-Encoders (VAEs). The VAEs are special Auto-Encoders which use a  KL divergence regularizer along with the reconstruction error. This regularizer forces the high  dimensional latent space to become regular[2], and a sufficiently smooth latent space allows for  disentanglement of latent dimensions. 
If the VAE is properly trained, the disentanglement of latent dimensions here essentially means that  each of these dimensions represents a specific feature about the input data, and varying them will  not affect the other[3]. For example, one of the latent dimensions may learn to control colors[3],  while the other one can learn the arms of the Baxter robot[4] as shown in the pictures below: 
  
Figure 1. Baxter robot arms 
In this project, the focus is to train VAEs to disentangle the self of the robot from the environment.  Secondly, detect the dimensions which learn the arms as shown in the images above, and evaluate  the hypotheses that will be stated in the upcoming sections. Moreover, proper disentanglement will  enable the robot to imagine its self in new environments. Concretely, this means the robot attains  some self-awareness using a VAE and imagines itself in new surroundings.  
Imagining itself in new surroundings increases the productivity of the robot[5]. The paper in [6]  discusses Level 1 self-awareness where a robot can distinguish itself spatially from its surrounding.  This project also builds on that idea[6] by using a generative network(VAE) instead of a deterministic  network[6]. 

