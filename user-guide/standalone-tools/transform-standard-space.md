# Transforming cells to standard space

To transform cell positions from the coordinate space of the raw data to that of another coordinate framework \(usually the atlas\).

```bash
cellfinder_cell_standard --cells /path/to/classified_cells.xml --transformation /path/to/control_point_file.nii --ref /path/to/reference_image.nii -o /path/to/output/directory -x 2 -y 2 -z 5
```

## Arguments

### Mandatory

* `--cells`  Path of the xml file containing cells to be transformed.                        
* `--transformation` Path to the control point file \(from niftyreg or cellfinder registration\)
* `--ref` Reference nii image, in the same space as the downsampled raw data
* `-o` or `--output-dir` Output directory

{% hint style="warning" %}
You must also specify the pixel sizes, see [Specifying pixel size](../usage/specifying-pixel-size.md)
{% endhint %}

### The following options can also be used:

* `--transform-all` Transform all cell positions \(including artifacts\).
* `----registration-config` To supply your own, custom registration configuration file.

**Performance/debugging**

* `-V` or `--verbose` Increase verbosity of statements printed to console \(all debug information is saved to file regardless of this flag\)
* `--n-free-cpus` The number of CPU cores on the machine to leave unused by the program to spare resources.

**All other options \(and their defaults\) can be round by running:**

```bash
cellfinder_cell_standard -h
```

\`\`

