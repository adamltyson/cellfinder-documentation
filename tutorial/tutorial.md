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

### Instructions

#### Setting up

* First install cellfinder, following the [Installation](../installation/installation.md) guide.
*  Download the data from [here](https://gin.g-node.org/cellfinder/data/raw/master/brainreg/test_brain.zip) \(it will take a long time to download\).
* Unzip the data to a directory of your choice \(doesn't matter where\). You should end up with a directory called `test_brain` with two directories, each containing 2800 images.
* Open a terminal \(Linux\) or your command prompt \(Windows\)
* Activate your [conda environment ](../installation/using-conda.md)

{% hint style="info" %}
The test data supplied is purposefully not the "best". It has some artefacts such as fluorescent vasculature, bright spots of the brain surface and stitching artefacts. 

The aim of this tutorial is not to show cellfinder performing perfectly, but to illustrate how it deals with less than perfect data, and how to improve the performance. 
{% endhint %}

#### Run cellfinder

To run cellfinder, you need to know:

* Where your data is \(in this case, it's the path to the `test_brain` directory\)
* Where you want to save the output data \(we'll just save it into a directory called `cellfinder_output`in the same directory as the `test_brain`\)
* The pixel sizes of your data in microns \(see [Specifying pixel size](../user-guide/usage/specifying-pixel-size.md) for details\). In this case, our data is 2um per pixel in x and y \(in the coronal plane\) and 5um in z \(the spacing of each plane\).
* The orientation of your data. For registration 
* Which atlas you want to use \(you can see which are available by running `brainglobe list`. In this case, we want to use a mouse atlas \(as that's what our data is\), and we'll use the 10um version of the [Allen Mouse Brain Atlas](https://mouse.brain-map.org/static/atlas). 



