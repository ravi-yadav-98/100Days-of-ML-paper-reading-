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


### Experiment:
   - cGAN method is applied on both graphics (i.e photo generation) and Vision (image semantic segmentation) tasks
   - Sementaic segmentation to image -->  CityScapes datasets
   - map to aerial photo --> Google maps
   -  decent results can be optained using small datasets( 400 images)
 
 ### Evaluating metrics:
  - Evaluating the quality of synthesized images is an open and difficult problem
  -  traditional metrices: per pixel-mean squared error
  -  run real vs fake on amazon mechanical turk
  -  For graphics problems like colorization and photo generation, plausibility to a human observer is often the ultimate
goal
  -  Inception score --> opbject detection
  -  semntic interpretability
  -  FCN - Score  --> Sementics segmentation
 
 ### Objective function:
  - L1 --> alone gives blurry images
  - cGAN --> alone give sharper but visual artifacts
  - adding l1+cGAN (lambda =100) reduces artifacts
  - that adding an L1 term also encourages that the output respect the input, since the
L1 loss penalizes the distance between ground truth outputs, which correctly match the input, and synthesized outputs
 - On removing conditioning from discriminator (GAN) --> poor performance--> generator collapse
 - **Colorfullness** --> cGAN produces sharp images (making images more colorfull)
    -  L1 leads to grayish and blurr pixels
 
 ### Generator archtecture:
  - A U-Net architecture allows low-level information to shortcut across the network
  - The encoder-decoder is created simply by severing the skip connections in the UNet. 
  - The encoder-decoder is unable to learn to generate realistic images in our experiments
  - U-Net trained with L1 loss optained better results than encoder-decoder
  
  ### pixelGAN -> PatchGAN  -> ImageGAN
   - We test the effect of varying the patch size N of our discriminator receptive field 
   - pixelGAN -->  1x1
   - pathchGAN --> 70x70
   - ImageGAN  ---> 286x286
   - pixel GAN  --> has not effect no spatial sharpness but does increases the colorfullness of image
   - COLOR HOSTOGRAM MATCHING(common problem in image processing )--> Can be solved using pxelGAN
   - 16x16 patchGAN --> Sharp output, Good FCN score but artifacts
   - 70x70 patch GAN  -->  improves artifacts , better FCN Score
   - 286x286 imageGAN  --> does't improve visual quality
  
  ### Conclusion:
  - the results in this paper suggest that conditional adversarial networks are a promising approach for many imageto-image translation tasks, especially those involving highly
structured graphical outputs. These networks learn a loss
adapted to the task and data at hand, which makes them applicable in a wide variety of settings



