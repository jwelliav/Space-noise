##Generative Adversarial Networks to generate dark data.


We build a Generative adversarial network with the goal of generating dark data of the 
WFC3 camera in the Hubble space telescope. We gather the data from the MAST archive. We 
separate out the files obtained into flt and flc files and in this notebook proceed as follows.

1)We create the dataset we are interested in. By this we mean, we extract numpy arrays from the 
flt files which are in FITS format and take every such numpy image and cut it into chunks of size 1024*1024.

2)We try and understand the distribution of data in the images, and calculate the mean and variance 
of the distributions. These values will be of use later when we normalize the data.

3)We create dataloader which we use to feed into the GAN. Note that this requires a custom loader 
since we work with numpy arrays.

4)We create the discrimator and generator. The architecture for both networks is along the lines of pytorch examples.

5)We then train the network.
