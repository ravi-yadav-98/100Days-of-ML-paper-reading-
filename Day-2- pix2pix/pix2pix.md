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
 - pix2pix is not application specific—it can be applied to a wide range of tasks, including synthesizing photos from label maps, generating colorized photos from black and white images, turning Google Maps photos into aerial images, and even transforming sketches into photos.
-  **These all problems are related to map pixel to pixel**
### cGAN:-
  - **Conditional adversarial nets are a general-purpose solution that appears to work well on a wide variety of these problems.**
  -  In cGAN both the generator and discriminator are conditioned on some sort of auxiliary information such as class labels or data from other modalities.
  -  As a result, the ideal model can learn multi-modal mapping from inputs to outputs by feeding it with different contextual information.
  -  cGANs are used for image2image translation, text to image , video generation, 
  -  In traditional GAN,  there is no way to control the types of images that are generated other than trying to figure out the complex relationship between the latent space input to the generator and the generated images.


### Network Architecture:
-  **The architecture of your network will contain**
      -    A generator with a U-Net-based architecture.
      -    A discriminator represented by a convolutional PatchGAN classifier (proposed in the pix2pix paper).
- The discriminator is provided both with a source image and the target image and must determine whether the target is a plausible transformation of the source image.
- The generator is trained via adversarial loss, which encourages the generator to generate plausible images in the target domain.
-  The generator is also updated via L1 loss measured between the generated image and the expected output images
-  
