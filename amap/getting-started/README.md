---
description: How to register your data to the template
---

# User guide

## Basic usage

```bash
amap /path/to/raw/data /path/to/output/directory -x 2 -y 2 -z 5
```

{% hint style="info" %}
Full command-line arguments are available with `amap -h`
{% endhint %}

{% hint style="warning" %}
If you have any spaces in your file-path, please enclose it in quotation marks, otherwise amap will interpret it as two inputs, separated by a space.

**i.e. `"/path/to/my data"` not `path/to/my data`.** 
{% endhint %}

## Arguments

### Mandatory

* Path to the directory of the images. \(Can also be a text file pointing to the files\)
* Output directory for all intermediate and final results

{% hint style="warning" %}
You must also specify the pixel sizes, see [Specifying pixel size](../../user-guide/usage/specifying-pixel-size.md)
{% endhint %}

### Additional options

* `-d` or `--downsample` Paths to N additional channels to downsample to the same coordinate space.
* `--no-save-downsampled` Don't save the downsampled brain before filtering.
* `--registration-config` To supply your own, custom registration configuration file
* `--sort-input-file` If set to true, the input text file will be sorted using natural sorting. This means that the file paths will be sorted as would be expected by a human and not purely alphabetically

#### Misc options

* `--n-free-cpus` The number of CPU cores on the machine to leave unused by the program to spare resources.
* `--debug` Debug mode. Will increase verbosity of logging and save all intermediate files for diagnosis of software issues.

### Input data orientation

If your data does not match the NifTI standard orientation \(origin is the most ventral, posterior, left voxel\), then please see [Image orientation](image-orientation.md) to reorient the atlas

### Registration options

To change how the actual registration performs, see [Registration parameters](registration-parameters.md)

### Visualisation options

* `--no-boundaries` Do not precompute the outline images \(if you don't want to use `amap_vis`\)

## Visualisation

To visualise your data, please see [Viewing registration results](../../user-guide/visualisation/registration-viewer.md)

