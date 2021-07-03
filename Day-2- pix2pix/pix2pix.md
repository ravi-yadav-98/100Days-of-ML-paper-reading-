## Day:02 - 02 July 2021: pix2 pix
### Paper: Image-to-Image Translation with Conditional Adversarial Networks - cGAN
### [paper link:](https://arxiv.org/pdf/1611.07004.pdf)
-  conditional adversarial networks as ageneral-purpose solution to image-to-image translation problems
-   Many problems in image processing, graphics, and vision involve translating an input image into a corresponding output image.
-   example: 
    1. black-white to color image
    2. day to night image
    3. sketch to image 
    4. edge to imgae
    5. labels(segementaion) to real image
-  **These all problems are related to map pixel to pixel**
### cGAN:-
  - **Conditional adversarial nets are a general-purpose solution that appears to work well on a wide variety of these problems.**
  -  In cGAN both the generator and discriminator are conditioned on some sort of auxiliary information such as class labels or data from other modalities.
  -  As a result, the ideal model can learn multi-modal mapping from inputs to outputs by feeding it with different contextual information.
  -  cGANs are used for image2image translation, text to image , video generation, 
  -  In traditional GAN,  there is no way to control the types of images that are generated other than trying to figure out the complex relationship between the latent space input to the generator and the generated images.
