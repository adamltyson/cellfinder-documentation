# Cropping xml file

To "crop" an xml file, i.e. only include cell coordinates corresponding to given anatomical areas.

```bash
    cellfinder_xml_crop --xml-dir xml_directory --structures-file chosen_structures.csv --registered-atlas registered_atlas.nii --hemispheres hemispheres.nii
```

## Arguments

Run `cellfinder_xml_crop -h` to see all options.

### Mandatory

* `--xml-dir` Directory containing xml files to be cropped
* `--structures-file` Curated csv structure list \(as per the allen brain atlas csv\)
* `--registered-atlas` The path to the atlas registered to the sample brain
* `--hemispheres` The atlas with just the hemispheres encoded

{% hint style="warning" %}
You must also specify the pixel sizes, see [Specifying pixel size](../usage/specifying-pixel-size.md)
{% endhint %}

### The following options may also need to be used:

* `--hemisphere-query` Which hemisphere to keep \(1 or 2\). Default: 0 \(all\)

\*\*\*\*

