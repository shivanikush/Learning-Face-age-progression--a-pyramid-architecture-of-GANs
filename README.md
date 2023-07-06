# Learning Face age progression- A Pyramid architecture of GANs
![Generic badge](https://img.shields.io/badge/Deep_Learning:-green.svg) ![Generic badge](https://img.shields.io/badge/Python-V3:-blue.svg)
![Generic badge](https://img.shields.io/badge/PyTorch:-green.svg)  ![Generic badge](https://img.shields.io/badge/GANs:-blue.svg)    ![Generic badge](https://img.shields.io/badge/Image_Processing:-green.svg)  ![Generic badge](https://img.shields.io/badge/Face_Age_Progression:-orange.svg)  ![Generic badge](https://img.shields.io/badge/Computer_Vision:-red.svg)
# Abstract
<br>
Since the face age progression deals with addressing the two main aspects, i.e. aging
accuracy and identity permanence, a Generative Adversarial Network is employed to model
restraint for the inherent subject specific characteristics as well as the age- specific changes in
faces with time. <br>
For generating more realistic facial details pyramidal adversarial discriminator is utilised
which models the effects of aging in a more advanced manner. 

# Goals/Objectives
Research in the face age progression can be employed in finding out the subjects that went
missing, in our case we will be analyzing on new born babies which can further be used by
the cops to search for the missing baby even after years he/she went missing. 
# Introduction
Age progression is the method of altering the facial images to demonstrate the consequences
of aging on the face of an individual.
The main reason behind opting for GAN in age progression is as follows:
  1. It facilitates age estimation and face verification while keeping the issues of aging
    effect generation as well as identity preservation,
  2. In the previous study forehead and hair components of face is not kept under
    considerations. 
# Previous Work
While solving the problem of face age progression innate complexity of physical aging and
interferences occurring due to the other factors makes it harder. There are many attempts that
have been employed for tackling the above problem:
  1. A compositional and dynamic model was employed where compositional model
    represent the faces in distinct age groups by hierarchy of And-Or-Graph(And nodes
    fragments the face into finer details i.e. hair, wrinkles, etc; Or nodes depicts the
    variety of face by substitutes). It is modelled as Markov process or the parse graph on
    the basis of two important aspects of face age progression i.e. accuracy and identity
    preservation [4].
 2. Analyzing the skin’s anatomical structure, a 3 layered dynamic skin model to
counterfeit wrinkles [5],
There are many other methods that were employed for face age progression, but in our work
we will be implementing face age progression with the help of GANs. <br>

# Method
_Overview_ <br>
A typical GAN consists of a generator G and a discriminator D which is trained with the help
of adversarial nets in iterations.
The generative network comprises of both encoder as well as decoder.
When the infant face is given as an input the generator make use of strided convolution layers
to encode it to a latent space.
# Dataset
We collected the dataset from CACD [1] is a comprehensive face dataset with a wide age
range 0-116. It consists of 20,000 facial images both augmented as well as unaugmentated
which is labelled as age, gender and ethnicity.
# Method
We will be making use of the method cited in Learning Face Age Progression:A pyramid
Architecture of GANs [2]. <br>
Using CACD dataset, we will be heading towards preprocessing the image data for finding
out missing images. After the images are preprocessed it will be fed to the discriminator.
In generator transformation of age into a target image space is attained by a strided
convolutional layers, by making use of instance normalization, orthogonal weight
normalization and ReLU non-linearity activation. For making the input and output size
uniform, paddings are added. <br>
In discriminator the pyramidal architecture is employed, actual faces and the output generated
by the Generator is fed to the discriminator for obtaining more intense age-specific facial
details, throughout training. Meanwhile, Batch Normalization and LeakyReLU is utilized at
each convolutional layer, except the last one in each pathway. <br>
The training process decreases the loss of Generator to Discriminator along with loss of
Generator to Generator, to generate more photorealistic image in a fine-grained manner.
For identity preservation we will be using the work done in Towards Open-Set Identity
Preserving Face Synthesis [3], as it incorporates asymmetric loss function for training the
input face image to generate an identity vector along with any other input face image to
withdraw an attribute vector containing pose, emotions and illumination,etc. <br>

# References
[1] CACD database. https://www.v7labs.com/open-datasets/cacd. <br>
[2]Hongyu Yang, Di Huang, Yunhong Wang, Anil K. Jain. 2019 Learning Continuous
Face Age Progression: A Pyramid of GANs: 32-38 <br>

[3] Jianmin Bao, Dong Chen, Fang Wen, Houqiang Li, Gang Hua. 2018 Towards Open-
Set Identity Preserving Face Synthesis. <br>

[4] J. Suo, S. C. Zhu, S. Shan, and X. Chen. A compositional and dynamic model for face
aging. IEEE PAMI, 32(3):385–401, Mar. 2010. 1, 5 <br>
[5] Y. Wu, N.M. Thalmann, and D. Thalmann. A plastic-visco-elastic model for wrinkles
in facial animation and skin aging. In PG, pages 201,214, 1994. 1,2 <br>
