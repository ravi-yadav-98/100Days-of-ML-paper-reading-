## ProGAN: How NVIDIA Generated Images of Unprecedented Quality
- Improve quality and variation of generated image

### Major limitation of GAN:
- Model collapse: --> Discriminator wins the game, Gradient of generator becomes very less so it start producing one type of image every time
- Problem with generating high resolution images (easily detected by discriminator): >512px
- **I should note, some image-to-image translation techniques can handle high resolutions, 
but that is a different task, since those only learn to change surface-level features of an input image, and are not generating an entirely new image from scratch.**


### Toward Higher Image Resolutions : ProGAN : Growing GANs
-  Instead of attempting to train all layers of the generator and discriminator at once — as is normally done — 
the team gradually grew their GAN, one layer at a time, to handle progressively higher resolution versions of the images.
-  The ProGAN starts out generating very low resolution images. When training stabilizes, a new layer is added and the resolution is doubled. 
This continues until the output reaches the desired resolution. By progressively growing the networks in this 
fashion, high-level structure is learned first, and training is stabilized.
-  By increasing the resolution gradually, we are continuously asking the networks to learn a much simpler piece of the overall problem. 
-  This improves the quality of the final image by reducing the likelihood that the network will get some high-level structure drastically wrong.
-  ProGAN generally trained about 2–6 times faster than a corresponding traditional GAN
-  DCGAN used transpose convolutions to change the representation size. In constrast, ProGAN uses nearest neighbors for upscaling and average pooling for downscaling
-  
