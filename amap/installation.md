---
description: Installing amap
---

# Installation

{% hint style="warning" %}
If you already have cellfinder, then amap has been installed for you.
{% endhint %}

## Introduction

amap is included with cellfinder. Unless you have a particular reason not to, I would install cellfinder as this will install all the packages you may need. See [cellfinder installation](../installation/installation.md).

If you know what you're doing just run:

```bash
pip install amap
```

{% hint style="info" %}
If you're not completely sure what you're doing, read on.
{% endhint %}

## Requirements

To run amap you will need a fairly high-powered computer running Windows or Linux  \(see [system requirements](../installation/system-requirements.md) for details\). In particular, to use some of the atlases, you may need at least 32GB of RAM.

## Setting up your machine

### Installing Python

amap is written in Python, and so needs a functional Python installation. Your machine may already have Python installed, but **I recommend installing miniconda**. 

**See** [**Using conda**](../installation/using-conda.md) **for details.** 

{% hint style="danger" %}
amap should run on any type of Python installation, but if you don't use conda, I may not be able to help you.
{% endhint %}

## Installing amap

{% hint style="info" %}
Remember to activate your conda environment before doing anything
{% endhint %}

```bash
pip install amap
```

## Download atlas and trained classification models \(optional\)

When you run amap, it will download the files it needs \(e.g. the atlas\). If you want to save time later, or you know you won't have an internet connection when you run amap you can download these in advance. See [downloading files](downloading-files.md) for details.

