---
description: Getting started with cellfinder
---

# Tutorial

{% hint style="danger" %}
**Still a work in progress. The test data is not yet uploaded**
{% endhint %}

Although cellfinder is designed to be easy to install and use, if you're coming to it with fresh eyes, it's not always clear where to start. We provide an example brain to get you started, and also to illustrate how to play with the parameters to better suit your data.

{% hint style="warning" %}
**The test dataset is large** \(~250GB\). It is recommended that you try this tutorial out on the fastest machine you have, with the fastest hard drive possible \(ideally SSD\) and an NVIDIA GPU. See [System requirements](../installation/system-requirements.md) for more details.
{% endhint %}

## Instructions

### Setting up

* First install cellfinder, following the [Installation](../installation/installation.md) guide.
*  Download the data from [here](https://gin.g-node.org/cellfinder/data/raw/master/brainreg/test_brain.zip) \(it will take a long time to download\).
* Unzip the data to a directory of your choice \(doesn't matter where\). You should end up with a directory called `test_brain` with two directories, each containing 2800 images.
* Open a terminal \(Linux\) or your command prompt \(Windows\)
* Navigate to the directory containing the `test_brain` directory \(e.g. using `cd`\)
* Activate your [conda environment ](../installation/using-conda.md)

{% hint style="info" %}
The test data supplied is purposefully not the "best". It has some artefacts such as fluorescent vasculature, bright spots of the brain surface and stitching artefacts. 

The aim of this tutorial is not to show cellfinder performing perfectly, but to illustrate how it deals with less than perfect data, and how to improve the performance. 
{% endhint %}

#### Before you start

To run cellfinder, you need to know:

* Where your data is \(in this case, it's the path to the `test_brain` directory\)
* Which image is the primary signal channel \(the one with the labelled cells\) and which is the secondary autofluorescence channel. In this case, `test_brain/ch00` is the signal channel and `test_brain/ch01` is the autofluroescence channel
* Where you want to save the output data \(we'll just save it into a directory called `cellfinder_output`in the same directory as the `test_brain`\)
* The pixel sizes of your data in microns \(see [Specifying pixel size](../user-guide/usage/specifying-pixel-size.md) for details\). In this case, our data is 2um per pixel in x and y \(in the coronal plane\) and 5um in z \(the spacing of each plane\).
* The orientation of your data. For atlas registration \(using [brainreg](https://docs.brainglobe.info/brainreg/introduction)\) the software needs to know how you acquired your data \(coronal, saggital etc.\). For this cellfinder uses [bg-space](https://github.com/brainglobe/bg-space). Full details on how to enter your data orientation can be found [here](https://docs.brainglobe.info/brainreg/user-guide#input-data-orientation), but for this tutorial, the orientation is `psl`, which means that the data origin is the most **p**osterior, **s**uperior, **l**eft voxel.  
* Which atlas you want to use \(you can see which are available by running `brainglobe list`. In this case, we want to use a mouse atlas \(as that's what our data is\), and we'll use the 10um version of the [Allen Mouse Brain Atlas](https://mouse.brain-map.org/static/atlas). 

### Running cellfinder

cellfinder runs with a single command, with various arguments that are detailed in [Command line options](../user-guide/usage/).  To analyse the example data, the flags we need are:

* `-s` The primary **s**ignal channel: `test_brain/ch00`
* `-b` The secondary autofluorescence channel \(or **b**ackground\): `test_brain/ch01`
* `-o` The **o**utput directory :  `test_brain/output`
* `-x` The pixel spacing in the first dimension \(left to right on a single plane in an image\): `2`
* `-y` The pixel spacing in the second dimension \(top to bottom on a single plane in an image\): `2`
* `-z` The pixel spacing in the third dimension \(the plane spacing\): 5
* `--orientation` The data orientation: `psl`
* `--atlas` The atlas we want to use: `allen_mouse_10um`

Putting this all together into a single command gives:

```text
cellfinder -s test_brain/ch00 -b test_brain/ch01 -o test_brain/output -x 2 -y 2 -z 5 --orientation psl --atlas allen_mouse_10um
```

This command will take quite a long time \(anywhere from 2-10 hours\) to run, depending on:

* The speed of the disk the data is stored on
* The CPU speed and number of cores
* The GPU you have

If you just want to check that everything is working, we can speed everything up by:

* Only analysing part of the brain using the flags: `--start-plane 1500 --end-plane 1550`
* Using a lower-resolution atlas, using the flag: `--atlas allen_mouse_25um`

```text
cellfinder -s test_brain/ch00 -b test_brain/ch01 -o test_brain/output -x 2 -y 2 -z 5 --orientation psl --atlas allen_mouse_25um --start-plane 1500 --end-plane 1550
```

{% hint style="warning" %}
If your machine has less than 32GB of RAM, you should use the `allen_mouse_25um` atlas either way, as registration with the high-resolution atlas requires about 30GB for this image.
{% endhint %}

### Inspecting the results



#### Visualising cell detection performance

cellfinder comes with a plugin for [napari](https://napari.org/) for easily visualising the results. To open napari, just run `napari` from your command line, and a viewer window should pop up.

Into the window, then drag and drop:

* The signal channel directory \(`test_brain/ch00`\)
* The entire cellfinder output directory

