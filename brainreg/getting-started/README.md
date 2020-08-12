---
description: How to register your data to the template
---

# User guide

## Basic usage

```bash
brainreg /path/to/raw/data /path/to/output/directory -x 2 -y 2 -z 5
```

{% hint style="info" %}
Full command-line arguments are available with `brainreg -h`
{% endhint %}

{% hint style="warning" %}
If you have any spaces in your file-path, please enclose it in quotation marks, otherwise brainreg will interpret it as two inputs, separated by a space.

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
* `--sort-input-file` If set to true, the input text file will be sorted using natural sorting. This means that the file paths will be sorted as would be expected by a human and not purely alphabetically

#### Misc options

* `--n-free-cpus` The number of CPU cores on the machine to leave unused by the program to spare resources.
* `--debug` Debug mode. Will increase verbosity of logging and save all intermediate files for diagnosis of software issues.

### Atlas

By default, brainreg will use the 25um version of the [Allen Mouse Brain Atlas](https://mouse.brain-map.org/). To use another atlas \(e.g. for another species, or another resolution\), you must use the `--atlas` flag, followed by the string describing the atlas, e.g.:

```bash
--atlas allen_mouse_50um
```

{% hint style="info" %}
To find out which atlases are available, once brainreg is installed, please run `brainglobe list`. The name of the resulting atlases is the string to pass with the `--atlas` flag.
{% endhint %}

### Registration backend

To change the registration algorithm used, use the `--backend` flag. The default is `niftyreg` as that is currently the only option.

### Input data orientation

If your data does not match the [brainglobe](https://github.com/brainglobe) default orientation \(the origin voxel is the most anterior, superior, left-most voxel, then you must specify the orientation by using the `--orientation` flag. What follows must be a string in the [bg-space](https://github.com/brainglobe/bg-space) "initials" form, to describe the origin voxel.

{% hint style="info" %}
When you work with a stack, the origin is the upper left corner when you show the first element `stack[0, :, :]` with matplotlib or when you open the stack with ImageJ. First dimension is the one that you are slicing, the second the height of the image, and the third the width of the image.
{% endhint %}

If the origin of your data \(first, top left voxel\) is the most anterior, superior, left part of the brain, then the orientation string would be "asl" \(anterior, superior, left\), and you would use:

```bash
--orientation asl
```

{% hint style="warning" %}
The order of the three initials must be the same as the axis order \(sliced plane, height, width\)
{% endhint %}

### Registration options

To change how the actual registration performs, see [Registration parameters](registration-parameters.md)



