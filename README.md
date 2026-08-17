# GEOMETRIC TRANSFORMATIONS USING OPENCV

## AIM

To write a Python program using OpenCV to perform various geometric transformations on an image, such as translation, scaling, shearing, reflection, rotation, and cropping.

## SOFTWARE USED

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (`cv2`)
* NumPy
* Matplotlib

## ALGORITHM

### Step 1: Import Libraries

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2: Read the Image

Read the input image in color mode and display the original image.

### Step 3: Image Translation

* Create a translation matrix.
* Shift the image 100 pixels horizontally and 50 pixels vertically.
* Apply the transformation using `cv2.warpAffine()`.
* Display the translated image.

### Step 4: Image Scaling

* Define horizontal and vertical scaling factors.
* Resize the image using `cv2.resize()`.
* Display the scaled image.

### Step 5: Image Shearing

* Create a shearing transformation matrix.
* Apply horizontal and vertical shearing.
* Use `cv2.warpAffine()` to transform the image.
* Display the sheared image.

### Step 6: Image Reflection

* Perform image flipping using `cv2.flip()`.
* Apply horizontal, vertical, and both-axis reflections.
* Display the reflected images.

### Step 7: Image Rotation

* Find the image height and width.
* Set the center of rotation.
* Create a rotation matrix using `cv2.getRotationMatrix2D()`.
* Rotate the image using `cv2.warpAffine()`.
* Display the rotated image.

### Step 8: Image Cropping

* Define the starting coordinates and crop dimensions.
* Crop the required region using array slicing.
* Display the cropped image.

## PROGRAM

### Developed By:

**Name:** SAHITH M
**Register No:** 212224230236

### Step 1: Import Libraries and Read Image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread("image.jpg")

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
plt.show()
```
<img width="764" height="383" alt="image" src="https://github.com/user-attachments/assets/af312d56-35d2-4f73-8b01-c4bd8998bac2" />

### Step 2: Image Translation

```python
tx, ty = 100, 50

M_translation = np.float32([
    [1, 0, tx],
    [0, 1, ty]
])

translated_image = cv2.warpAffine(
    image,
    M_translation,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')
plt.show()
```
<img width="731" height="432" alt="image" src="https://github.com/user-attachments/assets/0c439e9d-cea1-4045-92e7-7ec94feea656" />

### Step 3: Image Scaling

```python
fx, fy = 5.0, 2.0

scaled_image = cv2.resize(
    image,
    None,
    fx=fx,
    fy=fy,
    interpolation=cv2.INTER_LINEAR
)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')
plt.show()
```
<img width="750" height="226" alt="image" src="https://github.com/user-attachments/assets/7ab9d62f-3312-4eb9-b63d-9190e4db6727" />

### Step 4: Image Shearing

```python
shear_matrix = np.float32([
    [1, 0.5, 0],
    [0.5, 1, 0]
])

sheared_image = cv2.warpAffine(
    image,
    shear_matrix,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')
plt.show()
```
<img width="697" height="428" alt="image" src="https://github.com/user-attachments/assets/e7ae8f83-ab77-46a2-9f5b-0bcf23c599db" />

### Step 5: Image Reflection

```python
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')
plt.show()
```
<img width="784" height="439" alt="image" src="https://github.com/user-attachments/assets/0c1dd78a-31dd-42e9-9a1e-8943f9d4019c" />

### Step 6: Image Rotation

```python
(height, width) = image.shape[:2]

angle = 45
center = (width // 2, height // 2)

M_rotation = cv2.getRotationMatrix2D(
    center,
    angle,
    1
)

rotated_image = cv2.warpAffine(
    image,
    M_rotation,
    (width, height)
)

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')
plt.show()
```
<img width="685" height="431" alt="image" src="https://github.com/user-attachments/assets/c4baa367-4592-4f94-9fd9-ecafadb65b8b" />

### Step 7: Image Cropping

```python
x, y, w, h = 100, 100, 200, 150

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
<img width="715" height="551" alt="image" src="https://github.com/user-attachments/assets/96753fce-6eda-4ad4-bd95-fbbbaa2fdc3e" />

## OUTPUT

### Image Translation

* Original image is displayed.
* Translated image shifted right and down is displayed.

### Image Scaling

* Original image is displayed.
* Scaled image is displayed.

### Image Shearing

* Original image is displayed.
* Sheared image is displayed.

### Image Reflection

* Original image is displayed.
* Reflected image is displayed.

### Image Rotation

* Original image is displayed.
* 45° rotated image is displayed.

### Image Cropping

* Original image is displayed.
* Cropped image is displayed.

## RESULT

Thus, various geometric transformations such as **translation, scaling, shearing, reflection, rotation, and cropping** were successfully performed on an image using OpenCV.
