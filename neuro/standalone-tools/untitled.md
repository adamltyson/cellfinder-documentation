---
description: Visualise cell positions at a glance
---

# Heatmap generation

To generate a heatmap of detected cells, which shows cell distributions in a more intuitive way that showing individual cell positions:

![Overlay on raw data and segmentation from amap added separately](https://raw.githubusercontent.com/SainsburyWellcomeCentre/cellfinder/master/resources/heatmap.png)



## Usage

{% hint style="warning" %}
This tool is a work in progress, and the usage may change
{% endhint %}

```bash
    heatmap cell_classification.xml heatmap.nii raw_data registered_atlas.nii -x 2 -y 2 -z 5
```

## Arguments

Run `heatmap -h` to see all options.

### Positional arguments

* cellfinder classified cells file \(usually `cell_classification.xml`\)
* Output filename. Should end with '.nii'. If the containing directory doesn't exist, it will be created.
* Path to raw data \(just a single channel\). Used to find the shape of the raw image that the detected cell positions are defined in.
* Registered atlas file from amap \(typically run automatically in cellfinder\). File is usually `registered_atlas.nii`.

{% hint style="warning" %}
You must also specify the pixel sizes, see [Specifying pixel size](../../user-guide/usage/specifying-pixel-size.md)
{% endhint %}

### The following options may also need to be used:

* `--heatmap-bin` Heatmap bin size \(um of each edge of histogram cube\)
* `--heatmap-smoothing` Gaussian smoothing sigma, in um.
* `--no-mask-figs` Don't mask the figures \(removing any areas outside the brain, from e.g. smoothing\)

