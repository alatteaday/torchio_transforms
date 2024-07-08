# MRI Image Transformation Tutorial with `torchio`

This repository contains a Jupyter notebook that demonstrates the application of various MRI image transformations using the `torchio`` library. 
The transformations include adding artifacts such as motion, ghosting, spikes, bias fields, Gaussian noise, patch swaps, and Gaussian blur. 
This tutorial is useful for researchers and practitioners working in medical imaging who wish to simulate different types of MRI artifacts and enhance their image preprocessing pipelines.

## Requirements

To run this notebook, you'll need the following Python libraries:
* `torch`
* `torchio`
* `matplotlib`

## How to run

#### 1. Clone the repository
```
git clone https://github.com/alatteaday/torchio_transforms
cd torchio_transforms
```

#### 2. Install the dependencies using pip
```
pip install torch torchio matplotlib
```

#### 3. Open the Jupyter notebook
```
jupyter notebook tutorial.ipynb
```

#### 4. Load image
In the notebook, assign the directory of the image that you want to transform in the `tio.Subject` part. For example:
```
img = tio.Subject(
    t1=tio.ScalarImage('path/to/your/image')  # Replace with your image
)
``` 

#### 5. Transform the image by referring to the example codes
Refer to the example codes provided in the notebook to apply various transformations. 
Each example demonstrates how to add a specific artifact to the MRI image. 
The arguments are set to their default values.
For instance, to add random motion artifacts:
```
motion = transforms.RandomMotion(
    degrees=10, translation=10, num_transforms=2, image_interpolation='linear'
)
transformed_img = motion(img)
transformed_img.plot(figsize=(10,5))
```
