# Command line options

## Basic usage

To run cellfinder, use this general syntax

```bash
    cellfinder -s signal_channel_images  optional_signal_channel_images -b background_channel_images -o /path/to/output_directory -x 2 -y 2 -z 5 --orientation asl
```

{% hint style="info" %}
All options can be found by running `cellfinder -h`
{% endhint %}

## Arguments

### Mandatory

* `-s` or `--signal-planes-paths` Path to the directory of the signal files. Can also be a text file pointing to the files. **There can be as many signal channels as you like, and each will be treated independently**. 
* `b` or `--signal-planes-path` Path to the directory of the background files. Can also be a text file pointing to the files.  **This background channel will be used for all signal channels**
* `-o` or `--output-dir` Output directory for all intermediate and final results

{% hint style="warning" %}
You must also specify the pixel sizes \(see [Specifying pixel size](specifying-pixel-size.md)\) and the [orientation of your data](https://docs.brainglobe.info/brainreg/user-guide/image-orientation).
{% endhint %}

### The following options can also be used:

\*\*\*\*

**Only run parts of cellfinder**

If for some reason you don't want some parts of cellfinder to run, you can use the following options. If a part of the pipeline is required by another part it will be run \(i.e. `--no-detection` won't do anything unless `--no-classification` is also used\). cellfinder will attempt to work out what parts of the pipeline have already been run \(in a given output directory\) and not run them again if appropriate.

* `--no-registration` Do not run registration 
* `--no-detection` Do not run cell candidate detection
* `--no-classification` Do not run cell classification
* `--no-analyse`Do not not analyse and export cell positions
* `--no-figures` Do not create figures \(e.g. heatmap\)

**Figures options**

Figures cannot yet be customised much, but the current options are here:

* `--heatmap-smoothing` Gaussian smoothing sigma, in um.
* `--no-mask-figs` Don't mask the figures \(removing any areas outside the brain, from e.g. smoothing\)

**Performance, debugging and testing**

* `--debug` Increase verbosity of statements printed to console and save all intermediate files.
* `--n-free-cpus` The number of CPU cores on the machine to leave unused by the program to spare resources.
* `--max-ram` Maximum amount of RAM to use \(in GB\) - **not currently fully implemented for all parts of cellfinder**

Useful for testing or if you know your cells are only in a specific region

* `--start-plane` The first plane to process in the Z dimension
* `--end-plane` The last plane to process in the Z dimension

**Standard space options**

* `--transform-all` Transform all cell positions \(including artifacts\).

### Cell candidate detection options

To change how the initial cell candidate detection performs, see [Cell candidate detection](cell-candidate-detection.md).

### Cell classification options

To change how the cell candidate classification performs, see [Cell candidate classification](cell-candidate-classification.md).

### Registration options

To change how the actual registration performs, see [Registration parameters](https://docs.brainglobe.info/brainreg/user-guide/parameters).

### **Historical options**

If you have used old versions of cellfinder, there may be some options you want to change in [Historical options](historical-options.md)

\_\_

### 





