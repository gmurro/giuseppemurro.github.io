---
title: Install TextAttack on Windows
tags: [TextAttack, Adversarial-NLP, Windows]
style: fill 
color: primary 
description: Installation guide for TextAttack on Windows to perform adversarial NLP attacks using GPU acceleration.
---

Source: [Giuseppe Murro](https://medium.com/@gmurro/install-textattack-on-windows-bafe4d2dcd98)


Hi everyone! I’ve been struggling with the installation of a very good python library called TextAttack ([https://github.com/QData/TextAttack](https://github.com/QData/TextAttack)) since its setup is not so straightforward on a Windows machine. I’m sharing this with the hope of saving your time!

![](https://miro.medium.com/max/1400/1*AgQcCHsY5jGrqu45urSeyA.webp)

## **Requirements**

*   Windows 10/11
*   [Anaconda distribution](https://www.anaconda.com/products/distribution)

**1\. Install MSVC compiler**
-----------------------------

First of all, you need to install a compiler for the C, C++ and C++/CX programming languages for Windows. The simplest way is through [Visual Studio Community 2019 Installer](https://my.visualstudio.com/Downloads?q=visual%20studio%202019&wt.mc_id=o~msft~vscom~older-downloads), selecting the _Desktop development with C++ box_. A reboot could be needed after the installation.

![](https://miro.medium.com/max/1400/1*fXkb1TrZQnOJB-yGotLi4w.webp)

2\. Create a conda environment
------------------------------

Using Anaconda to create dedicated environments is always the best way to not mess up your python installation. Run the following commands in a terminal:

```
conda create -n textattack python=3.8
conda activate textattack
```

3\. Install PyCLD2
------------------

On Windows the installation of TextAttack cannot build the library pycld2 automatically, so you need to install it from [unofficial windows binaries](https://www.lfd.uci.edu/~gohlke/pythonlibs/).

In the PyCL2 section, there are several files, where _“cp\*\*”_ indicates the python version (e.g. cp38 stands for python 3.8). If you have a 64-bit Windows system, you have to download the file coloured in red.

![](https://miro.medium.com/max/1400/1*aSdr7FJ3nIbBjnJA7LLDFQ.webp)

To install it, run the following command in the same terminal as before:

```
cd Downloads
pip install pycld2-0.41-cp39-cp39-win\_amd64.whl
```

**4\. Install TextAttack**
--------------------------

Now you can proceed to install the TextAttack library:

```
pip install textattack
```

5\. CUDA Acceleration
---------------------

Now everything is setted up and you can start your coding session.

But in order to speed up the performance of TextAttack, you need to install both Tensorflow and Pytorch with CUDA compatibility if you have a NVIDIA GPU. My advice is to install the most recent CUDA version which is supported by both Tensorflow and Pytorch (according to the official [tf](https://www.tensorflow.org/install/source#gpu) and [torch](https://pytorch.org/get-started/previous-versions/) docs the newest version like 11.2 or 11.3 are not compatible with both). This is CUDA 11.0 and you can follow this [guide](https://docs.nvidia.com/cuda/archive/11.0/cuda-installation-guide-microsoft-windows/index.html).

Then if CUDA 11.0 is installed correctly (check with `nvcc -V`\` command), install Tensorflow and Pytorch on our conda environment with the following commands:

```
pip install tensorflow==2.4
pip install torch==1.7.1+cu110 torchvision==0.8.2+cu110 torchaudio==0.7.2 -f https://download.pytorch.org/whl/torch_stable.html
```