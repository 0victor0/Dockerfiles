#Dockerfiles

Repo for my Dockerfiles. Directories with arm_* are compatible with
ARM architecture.

##Config files
If you want to import config files, copy them into directory with Dockerfile.

##Quick tips

###Build images:

Go into directory then build image with:

        docker build . -t [name of image]

###Spin up containers:

From any directory, once you have started Docker daemon:

        docker run -it \
            -h [host name] \
            --name [container name] \
            -p [host port]:[container port] \   #if needed
            [image name] \
            [shell command]                     #if needed, like /bin/bash

###Attach container:

        docker attach [container name]

####Detach container:

        ctrl+p, ctrl+q

####Stop attached container:

        ctrl+d

