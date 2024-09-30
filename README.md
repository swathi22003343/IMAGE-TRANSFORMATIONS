# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

### Step 6:
Rotate the image using angle function.

## Program:

### Developed By: SWATHI D
### Register Number: 212222230154
```python
i)Image Translation
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = r"C:\Users\admin\Downloads\gray .jpg"
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```
```python
ii) Image Scaling
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = r"C:\Users\admin\Downloads\gray .jpg"
image = cv2.imread(image_url)

# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis

# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```

```python
iii)Image shearing
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = r"C:\Users\admin\Downloads\gray .jpg"
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)
```
```python
iv)Image Reflection
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = r"C:\Users\admin\Downloads\gray .jpg"
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

# Display original and reflected images
print("Original Image:")
show_image(image)
print("Reflected Horizontally:")
show_image(reflected_image_horizontal)
print("Reflected Vertically:")
show_image(reflected_image_vertical)
print("Reflected Both:")
show_image(reflected_image_both)

```
```python
v)Image Rotation
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = r"C:\Users\admin\Downloads\gray .jpg"
image = cv2.imread(image_url)

# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)
```
```python
vi)Image Cropping
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = r"C:\Users\admin\Downloads\gray .jpg"
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)
```
## Output:
### i)Image Translation
![image](https://github.com/user-attachments/assets/cad21cfa-a615-4109-9a7f-95963d1f9340)


### ii) Image Scaling
![image](https://github.com/user-attachments/assets/008c77a9-8edf-492d-b81a-7dcc2290b050)


### iii)Image shearing
![image](https://github.com/user-attachments/assets/c73a4734-e7cf-4a38-b1e4-4b80b6a2b420)


### iv)Image Reflection
![image](https://github.com/user-attachments/assets/b860fcb9-d130-4987-9130-e22ec61e636b)


![image](https://github.com/user-attachments/assets/b1825fa9-3528-4436-b077-94e97f2785d8)


### v)Image Rotation
![image](https://github.com/user-attachments/assets/1e55c46f-9de9-4d46-b6dd-e14b368ca121)



### vi)Image Cropping
![image](https://github.com/user-attachments/assets/e7b5b375-7b69-4684-85bf-6871e3224e8a)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
