---
description: Organising your Python environments with conda
---

# Using conda

## Simple introduction

**If you use cellfinder please use conda**

### Full introduction

Conda is a package and environment management system that allows you to:

* Install the correct version of Python to run cellfinder
* Install cellfinder without admin rights \(useful for shared machines and compute clusters\).
* Install cellfinder without affecting anyone elses software installation \(e.g. on a shared machine\).
* Install cellfinder without potentially messing up any important software on your machine.
* Install multiple \(potentially conflicting\) versions of software at the same time, and allow you to switch between the two. This is very useful if you want to keep using a specific version of cellfinder for one experiment, but try out some new features of the latest release for another.

{% hint style="info" %}
**You don't have to use conda, but it will make your life much easier, and it will make it much easier for me to provide help.** 
{% endhint %}

\(If you know what you're doing with virtual environments, feel free to ignore this, but conda does make [CUDA and cuDNN installation easier](setting-up-your-gpu.md#installing-cuda-and-cudnn)\).

## Installation

**N.B. If you already have** [**Anaconda**](https://www.anaconda.com/) **or** [**miniconda**](https://docs.conda.io/en/latest/miniconda.html) **you can skip this section.**

### Download miniconda

Download the correct version of miniconda from [here](https://docs.conda.io/en/latest/miniconda.html). You should download:

* The correct version for your operating system \(Linux/Windows/macOS etc.\)
* The **Python 3.x** version \(i.e. not the Python 2.7 version\)
* The 64-bit version \(in the unlikely event that you have a 32 bit machine, cellfinder probably won't work anyway\).

You can download [Anaconda](https://www.anaconda.com/) instead, but I recommend miniconda.

### Install miniconda

Follow the miniconda instructions for [Windows](https://conda.io/projects/conda/en/latest/user-guide/install/windows.html), [Linux](https://conda.io/projects/conda/en/latest/user-guide/install/linux.html) or [macOS](https://conda.io/projects/conda/en/latest/user-guide/install/macos.html).

### Check that conda is installed

N.B. conda is the program we are using, and is installed by both miniconda or Anaconda.

Open a new terminal window. On Linux and macOS, this is just called "Terminal", and on Windows, it will be called "Anaconda Prompt".

You should see a small screen with a prompt like:

```bash
(base) adam@adams-computer:~$ 
```

The `(base)` is the bit that tells you that conda is set up

## Setup your conda environment

### Create the environment

Open a terminal \(or Anaconda Prompt\) and type:

```bash
conda create --name cellfinder python=3.8
```

This will:

* Create a new conda environment \(a kind of walled-off area on your computer that shouldn't affect other parts\)
* Call it "cellfinder" \(so you can reference it later\)
* Install python version 3.8 into it. 

{% hint style="info" %}
You can call your environment whatever you like, and cellfinder will also work with Python 3.7, but I recommend 3.8.
{% endhint %}

### Activate the environment

```bash
conda activate cellfinder
```

If you called your environment something else, replace "cellfinder" with your custom name.

Your prompt should change to show the change from `(base)` to `(cellfinder)`:

```bash
(cellfinder) adam@adams-computer:~$ 
```

{% hint style="danger" %}
**You must run `conda activate cellfinder` whenever you open a new terminal window** to use cellfinder. If you don't see the `(cellfinder)` part of the prompt, the environment isn't activated
{% endhint %}

## Further details

The reason why we use conda environments \(other methods other than conda are available\) is to have separate Python installations. This way anything we do in the cellfinder environment shouldn't affect any of the other environments. 

If anything goes wrong, and cellfinder stops working \(and can't be fixed\), you can simply make a new environment, and start again. If you have any troubles though, [please get in touch](../general/getting-in-touch.md).

