## Day :01 StyleGAN Date: 27 June 2021
### [styleGAN paper link](https://arxiv.org/abs/1812.04948)
----------------------------------------------------------------------------
### "A Style-Based Generator Architecture for Generative Adversarial Networks"
 
1. **Introduction**
   - an alternative generator architecture for generative adversarial networks, borrowing from style transfer literature.
   - By NVIDIA 
   - Modified Genertor , Most of changes previously done were in only discriminator
   - proposed a new **Architecture of Generator**
   - In simple words, the generator in a StyleGAN makes small adjustments to the “style” of the image at each convolution layer in order to manipulate the image features for that layer.
   - Moreover, this new architecture is able to separate the high-level attributes (such as a person’s identity) from low-level attributes (such as their hairstyle) within an image.
   -  **This separation is what allows the GAN to change some attributes without affecting others.** For example, changing a person’s hairstyle in a given image.
   -   **the generator, is tasked with the generation of new data instances that it creates from random noise**
   -  **discriminator, evaluates these generated instances for authenticity.**
   -  The generative phase is influenced by the discriminative phase’s evaluation, and the discriminative phase makes comparisons between the original dataset and the generated samples.
   -  As training progresses, both networks keep getting smarter
   -  the generator at generating fake images and the discriminator at detecting their authenticity.
   - **By the time the model has been trained, the generator manages to create an image authentic enough that the discriminator can’t tell if it’s a fake or not**


2. **StyleGAN:
   -  **it allows for a factor of variability in generated images due to the addition of “styles” to images at each convolution layer.**
   -  Provide control on generator
   
   ![image](https://user-images.githubusercontent.com/85448160/123863120-cde1d680-d946-11eb-8423-8be0cea01389.png)

   -  The model starts off by generating new images, starting from a very low resolution (something like 4x4) and eventually building its way up to a final resolution of 1024x1024.
   -  **The main principle behind training the StyleGAN is this “progressive” method which was first used by NVIDIA in their ProGAN.**
   -  Progressive GAN (proGAN) reduces the limitations of traditional GAN i.e Model collapse
   -  in styleGAN: method---Specifically, this method causes two images to be generated and then combined by taking low-level features from one and high-level features from the other
   -  A mixing regularization technique is used by the generator, causing some percentage of both to appear in the output image.
   -  [ProGAN](https://towardsdatascience.com/progan-how-nvidia-generated-images-of-unprecedented-quality-51c98ec2cbd2)
   -  At every convolution layer, different styles can be used to generate an image:
   - middle styles with a resolution of 16x16 to 32x32, or fine styles with a resolution from 64x64 to 1024x1024.
   - Coarse styles govern high-level features such as the subject’s pose of in the image or the subject’s hair, face shape, etc. Middle styles control aspects such as facial features. Lastly, fine styles cover details in the image such as color of the eyes or other microstructures.
   - The StyleGAN architecture also adds noise on a per-pixel basis after each convolution layer for **stochastic variations:**
   - 
   - 
    
    
    
