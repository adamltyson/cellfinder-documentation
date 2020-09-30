# Introduction

{% hint style="danger" %}
**N.B. amap will not be developed further, in favour of** [**brainreg**](https://github.com/brainglobe/brainreg)**, which is based on** [**bg-atlasapi**](https://github.com/brainglobe/bg-atlasapi) **to support multiple species, atlases and resolutions.**

**amap will be supported for existing projects, but if you are starting a new project, please use** [**brainreg**](https://github.com/brainglobe/brainreg)**.**
{% endhint %}

{% hint style="info" %}
amap is included with cellfinder, and exists as a standalone tool if you do not need the cell detection part
{% endhint %}

## About

amap is the part of cellfinder that takes care of image registration and atlas-based segmentation. It is a Python port of [aMAP](https://github.com/SainsburyWellcomeCentre/aMAP/wiki) \(originally written in Java\), which has been [validated against human segmentation](https://www.nature.com/articles/ncomms11879).

The actual registration is carried out by [NiftyReg](http://cmictig.cs.ucl.ac.uk/wiki/index.php/NiftyReg).

## Details

The aim of amap is to register the template brain \(e.g. from the [Allen Reference Atlas](https://mouse.brain-map.org/static/atlas)\) to the sample image. Once this is complete, any other image in the template space can be aligned with the sample \(such as region annotations, for segmentation of the sample image\). The template to sample transformation can also be inverted, allowing sample images to be aligned in a common coordinate space.

To do this, the template and sample images are filtered, and then registered in a three step process \(reorientation, affine registration, and freeform registration.\) The resulting transform from template to standard space is then applied to the atlas.

Full details of the process are in the [original paper](https://www.nature.com/articles/ncomms11879).  

![Overview of the registration process](https://raw.githubusercontent.com/SainsburyWellcomeCentre/amap-python/master/resources/reg_process.png)

## Installation

```bash
pip install amap
```

{% hint style="info" %}
For detailed instructions see [Installation](installation.md)
{% endhint %}

## Usage

```bash
amap /path/to/raw/data /path/to/output/directory -x 2 -y 2 -z 5
```

{% hint style="info" %}
For more information see [Getting started](getting-started/)
{% endhint %}

### 



