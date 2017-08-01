# Introduction to TensorFlow

Welcome to the *Introduction to TensorFlow* online training.  These directories contain the course material.  In order to follow the lectures and do the exercises, you will want to ensure all of the Python packages you will need are installed and working before the course begins.

## Installation

All of the code we present uses Python 2.7.  A number of libraries beyond the standard library are used.  We recommend using the conda package manager to install the same versions that we are using, in a manner that won't interfere with your system packages.  Alternatively, you can create a docker container from the provided Dockerfile that will contain all the necessary Python modules.

### Conda

You may install either the full [Anaconda Package Manager](https://docs.continuum.io/anaconda/install) or the smaller [Miniconda system](http://conda.pydata.org/docs/install/quick.html).  The former will provide you with over 720 packages, ready to use; the latter will makes it easy to download them when needed.  Once one of these are installed, you can install the packages we will be using into a separate environment with
```bash
$ conda env create -f environment.yml
```

This will create a new conda environment named _oreillytf_.  It can be activated on Linux and OS X with
```bash
$ source activate oreillytf
```
or on Windows with
```
> activate oreillytf
```
Once in the environment, you can navigate to the course directory and launch the jupyter notebook server:
```
(oreillytf) $ jupyter notebook
```
The notebook server should display a URL for you to open.  Alternatively, open http://localhost:8888/, and enter the token displayed in the output to authenticate.

### Docker

Alternatively, you can run all of the Python and TensorFlow code within a Docker container.

First, install [Docker](https://www.docker.com/) on your system.
Then run these commands
```
docker build -t tensorflow-image .
```
This will build a docker image from `Dockerfile` and name it *tensorflow-image*.  Next, launch a container with this image with
```
docker run -p 8888:8888 -p 6006:6006 -t -i --name=tensorflow tensorflow-image
```
A Jupyter notebook server will automatically be started.  The URL to open should be printed out.  Alternatively, you can visit http://localhost:8888/ and enter the authentication token printed out.

Should you need to stop the container, you can restart it with
```
docker start -a -i tensorflow
```
Any changes made in the container will be preserved.  (Don't use `docker run` again, as it will make a new container without any of your modifications.)
