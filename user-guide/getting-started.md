---
description: How to get started with cellfinder
---

# Getting started

## Before you start

* Make sure that cellfinder is installed \(if not see [Installation](../installation/installation.md)\)
* Make sure that your data is organised as expected \(see [Data requirements](data-requirements.md)\)

{% hint style="info" %}
Make sure you activate your conda environment before running cellfinder
{% endhint %}

### Running cellfinder

cellfinder can be run with a single terminal command \(`cellfinder`\):

```text
    cellfinder -s signal_channel_images  -b background_channel_images -o /path/to/output_directory -x 2 -y 2 -z 5
```

Multiple channels can also be processed at once with the same registration: 

```text
cellfinder -s first_signal_channel_images  second_signal_channel_images -b background_channel_images -o /path/to/output_directory -x 2 -y 2 -z 5
```

However, there are many options to change what parts of the analysis are run, and how they are run. I recommend looking through the [Command line options](usage/).

{% hint style="warning" %}
If you have any spaces in your file-path, please enclose it in quotation marks, otherwise cellfinder will interpret it as two inputs, separated by a space.

**i.e. `"/path/to/my data"` not `path/to/my data`.** 
{% endhint %}

### Retraining the machine learning network to classify cells

The deep learning network included with cellfinder to classify cells as real cells or artefacts was trained on a very specific dataset. You will very likely need to retrain this if the classification is incorrect on your data. See [Training the network](untitled-1.md).

