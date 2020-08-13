---
description: What kind of data does cellfinder support?
---

# Data requirements

## Introduction

cellfinder was written to analyse certain kinds of whole brain microscopy datasets \(e.g. serial two-photon or lightsheet in cleared tissue\). Although we are working on supporting different kinds of data, currently, the data must fit these criteria:

### Image channels

For registration, you only need a single channel, but this is ideally a "background" channel, i.e. one with only autofluroescence, and no other strong signal. Typically we acquire the "signal" channels with red or green filters, and then the "background" channel with blue filters.

For cell detection, you will need two channels, the "signal" channel, and the "background" channel. The signal channel should contain brightly labelled cells \(e.g. from staining or viral injections\). The models supplied with cellfinder were trained on whole-cell labels, so if you have e.g. a nuclear marker, they will need to be retrained \(see [Training the network](untitled-1/)\). However, realistically, the network will need to be retrained for every new application

### Image structure

Although we hope to support more varied types of data soon, your images must currently:

* Cover the entire brain
* Be of sufficiently high resolution that cells appear in multiple planes \(i.e. &lt;10 micron axial spacing\)
* Contain planes that are registered to each other \(i.e. this is often not the case with slide scanners or manual acquisition\)

### Organisation

cellfinder expects that your data will be stored as a series of 2D tiff files. These can be in a single directory, or you can generate a text file that points to them. Different channels in your dataset must be in different directories, or text files.

{% hint style="warning" %}
Please ensure that none of the files or folders that you pass to cellfinder have a space in them. This should be fixed in the future, but for now, please use `/the_path/to/my_data` rather than `/the path/to/my data`
{% endhint %}

### Applications

Theoretically, the cell detection will work with any data, the registration is currently limited to adult mouse datasets \(but this will likely change soon\).

