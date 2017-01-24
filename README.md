#Dockerfiles

Repo for my Dockerfiles. Directories with arm_\* are compatible with ARM
architecture. Any builds at version >=1.0 can be pulled from [my Docker hub](https://hub.docker.com/r/victorclark/).

*Note that any Dockerfiles with versions less than 1.0 have not been verified.*

##Config files

Config files also included, useful for VM host machine setup.

##Quick tips

###Build images:

Go into directory then build image with:

        docker build . -t [name of image]

###Spin up containers:

Lots of ways to start containers, here's a suggestion after starting the Docker
daemon:

        docker run \ 
            -it \                                   #attach to STDIN
            -h [host name] \                        #change prompt
            --rm \                                  #remove after exit
            --name [container name] \               #persistent name if not using --rm
            --net=host \                            #useful for network analysis
            -v [host dir]:[container mount point] \ #if needed
            -p [host port]:[container port] \       #if needed
            [image name] \
            [shell command]                         #if needed, like /bin/bash

####Detach container:

        ctrl+p, ctrl+q

####Stop attached container:

        ctrl+d

###Attach running container:

        docker attach [container name]

###Run command on detached container:

        docker exec [container name] [command]

This is useful to see what's going on with the container. Not uncommon to verify
sanity with `docker exec some-container ps | grep some-process name`. 
