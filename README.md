# Text-independent-speaker-identification-applying-a-very-deep-CNN-and-transfer-learning
Repository cointener for experiments on inception v3 applied in text independent speaker identification task


## Install docker toolbox

1.- go to ![docker tollbox installer](https://docs.docker.com/v17.12/toolbox/toolbox_install_windows/)

2.- Make sure your Windows system supports Hardware Virtualization Technology and that virtualization is enabled


![Virtualization ok!](https://docs.docker.com/v17.12/toolbox/images/virtualization.png)

3.- The installer adds Docker Toolbox, VirtualBox, and Kitematic to your Applications folder. In this step, you start Docker Toolbox and run a simple Docker command. Verify:


![Install...ok!](https://docs.docker.com/v17.12/toolbox/images/icon-set.png)

## Pull the image 

1.- In docker terminal type:

     $ docker pull zned897/inceptionv3-repo:speakerIDv2
     $ docker run -it -d zned897/inceptionv3-repo:speakerIDv2
     $ docker ps -a 
     

