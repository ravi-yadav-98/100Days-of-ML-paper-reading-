## Types of GAN:
### DCGAN (deep convolution GAN)
- DCGANs are an improvement of GANs. They are more stable and generate higher quality images. In DCGAN, batch normalization is done in both networks,
 i.e the generator network and the discriminator network. They can be used for style transfer


### Conditional GAN (cGAN)
- These GANs use extra label information and result in better quality images and are able to control how generated images will look. 
cGANs learn to produce better images by exploiting the information fed to the model.
-

### stackGAN:
- The authors of this paper propose a solution to the problem of synthesizing high-quality images from text descriptions in computer vision. 
- They propose Stacked Generative Adversarial Networks (StackGAN) to generate 256x256 photo-realistic images conditioned on text descriptions.


### InforGAN
-  InfoGAN is an information-theoretic extension to the GAN that is able to learn disentangled representations in an unsupervised manner. 
InfoGANs are used when your dataset is very complex, when you’d like to train a cGAN and the dataset is not labelled, and when you’d like to 
see the most important features of your images.

### Wasserstein GANs(WGAN)
- WGANs change the loss function to include a Wasserstein distance. They have loss functions that correlate to image quality.

### Application of GAN
-  Predicting next frame in video
-  Increasing Resolution of an image
-  Text-to-Image Generation (stackGAN)
-  Image to image translation (pix2pix)
-  

