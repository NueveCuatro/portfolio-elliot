---
title: Releasing Image Processing Library on PyPI
publishDate: 2020-03-02 00:00:00
img: /assets/thumbnails/image-processing-lib-768.png
img_alt: a personn scanning a document whith his phone
description: A Complete Guide Publishing a Python library for public use is a rewarding experience. In this guide, we'll walk you through how to release a Python library to the Python Package Index (PyPI) using an example package called image-processing-lib.
tags:
  - Python
  - Computer vision
---

In today's blog post, I'm excited to share a Python library I've created to make life easier for my schoolmates during our lab sessions. I've included easy-to-use processing and display functions so you don't have to waste time, especially when dealing with issues like reading OpenCV images in Jupyter Notebooks. Read on to find out how you can make the most of this new tool!

### Table of Contents

- [Table of Contents](#table-of-contents)
- [Your project directory should have the following structure:](#your-project-directory-should-have-the-following-structure)
- [Writing Your Library](#writing-your-library)
- [Creating setup.py](#creating-setuppy)
- [Publishing to PyPI](#publishing-to-pypi)
- [Updating the Library](#updating-the-library)
- [Using image-processing-lib](#using-image-processing-lib)
- [Use the functions provided by the library](#use-the-functions-provided-by-the-library)
  - [Functions:](#functions)




### Your project directory should have the following structure:

```plaintext
image-processing-lib/
│
├── image-processing-lib/
│   ├── __init__.py
│   └── functions.py 
└── setup.py
├── README.md
```

### Writing Your Library
Your actual Python code resides in the inner image-processing-lib directory. For example, let's say functions.py contains utility functions for image processing.

### Creating setup.py
The setup.py file contains metadata about your library and its dependencies. Here's a sample:

```python
from setuptools import setup, find_packages

setup(
    name='image-processing-lib',
    version='0.1',
    packages=find_packages(),
    install_requires=[
        'numpy',
        'opencv-python',
        'matplotlib'
    ],
    author='Your Name',
    author_email='youremail@gmail.com',
    description='Image processing utilities',
    long_description=open('README.md').read(),
    long_description_content_type='text/markdown',
)
```

### Publishing to PyPI
Follow these steps to publish your package:

1. Create distribution packages:
```bash
python setup.py sdist bdist_wheel
```
2. Upload with Twine:
```bash
twine upload dist/*
```

### Updating the Library
If you need to make changes, increment the version number in setup.py and then run:

```bash
python setup.py sdist bdist_wheel
twine upload dist/*
```

### Using image-processing-lib
To use image-processing-lib in your project, you'll first need to install it:

```bash
pip install image-processing-lib
```
Then, you can use it in your Python code like this:

```python
import image_processing.functions as ip
```

### Use the functions provided by the library
The provided Python library offers a collection of functions to perform various image processing tasks using OpenCV and NumPy. The library provides functionalities like opening and converting images in different color spaces, displaying multiple images with labels, normalizing, flattening and unflattening images, binary conversion, splitting images into blocks, resizing, rotating, and enhancing images. Here is an explanation of what each function does and how to use it:

#### Functions:

1. `open_img()`:
Opens an image and converts it to a specific color space.
- **Parameters**:

    **img:** Path to the image or a NumPy array.

    **color_space**: Desired color space (RGB, HSV, etc.)

    **array32**: If True, the image is converted to float32.

    **uint8**: If True, the image is converted to uint8.

- **Returns**: Converted image as a NumPy array.

2. `display()` :
Displays multiple images with labels.
- **Parameters**:

    **args**: Multiple arguments for images and labels.

    **figsize**: Size of the figure.

    **nb_cols**: Number of columns for display.

3. `normalize_img()`:
Normalizes an image.
- **Parameters**:

    **img**: The image to normalize.

    **Returns**: Normalized image.

4. `flatten_unflatten()`:
Flattens or unflattens an image.
- **Parameters**:

    **img**: The image to flatten/unflatten.

    **flatten**: If True, flattens the image.

    **shape**: Desired shape for unflattening.

5. binary
Binarizes an image.
- **Parameters**:

    **img**: The image to binarize.

    **threshold**: Threshold value for binarization.

    **upto255**: If True, values will go up to 255.

6. `img2blocs()`:
Splits an image into smaller blocks.
- **Parameters**:

    **img**: The image to split.

    **bloc_size**: Size of each block.

    **padding_type**: Type of padding to apply.

7. `resize_img()`:
Resizes an image.
- **Parameters**:

    **img**: The image to resize.

    **width**: Desired width.

    **height**: Desired height.

8. `rotate_img()`:
Rotates an image.
- **Parameters**:

    **img**: The image to rotate.

    **angle**: Angle of rotation.

9. `enhance_img()`:
Enhances an image by adding noise, blur, or changing contrast.
- **Parameters**:
Various parameters for noise, blur, and contrast.
