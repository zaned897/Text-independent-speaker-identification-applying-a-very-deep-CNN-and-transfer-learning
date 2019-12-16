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
          CONTAINER ID        IMAGE                           COMMAND             CREATED             STATUS                                              
          657cfbcf1caf        zned897/inceptionv3-repo        "/bin/bash"         3 months ago        Up 4 weeks                       
     $ docker exec -it  657cfbcf1caf  bash # change  657cfbcf1caf for your own container ID
     
 ## Train and test
 
 1.- Move your images folder insede the contaier
     
     $ docker cp IMAGES_FOLDER_PATH 657cfbcf1caf:/data/ # change  657cfbcf1caf for your own container ID
     
 
 2.- For trainig data just run the command:
     
     root@657cfbcf1caf:~# cd / 
     root@657cfbcf1caf:/# python main_train.py your_train_folder_images_PATH # i.e. /data/trainig_voice/,also you can add hyperparameter as: --learning_rate=.005 --how_many_training_steps=100000
    
 3.- Testing the model. it just evaluate a single image at time

      root@657cfbcf1caf:/# python main_test.py your_test_image_PATH # i. e. /data/testing_voice/Al/Al_1.jpg
     
     
## Jupyter notebook running on docker container (optional)

1.- In docker:

     $ docker run -it -p 8888:8888 zned897/inceptionv3-repo:speakerIDv2
     
2.- In container:

     $ ./run_jupyter.sh --ip 0.0.0.0 --no-browser --allow-root
     
3.- In Host open chrome browser (preferably)

     localhost:8888/tree

