# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

# Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

# Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

# Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

# Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

# Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:

Developed By: THIRISHA A

Register Number: 212223040228
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('Tiger.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
<img width="489" height="351" alt="373125368-77f7f0f3-cc62-4f23-95f6-6ce418573eb2" src="https://github.com/user-attachments/assets/43512ba5-045e-483f-9fc8-f68a95c13255" />

i)Image Translation

```
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```

<img width="472" height="346" alt="373124835-8e2c786b-587a-4816-8ff9-3346f47a1205" src="https://github.com/user-attachments/assets/bcdadddd-013f-42e5-ae6d-9fba58b1b0e0" />

ii) Image Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
<img width="472" height="367" alt="373127307-f357adc7-dbfd-4eb1-9d10-8040c10a587c" src="https://github.com/user-attachments/assets/818df3a0-acd4-496d-b799-80f724bed548" />


iii)Image shearing
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
<img width="483" height="350" alt="373126156-0ec52705-500b-4a17-b46f-db6f167f1211" src="https://github.com/user-attachments/assets/f3c94159-af56-4567-b0b6-d3471585137a" />

iv)Image Reflection

```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```

<img width="471" height="354" alt="373127208-9c78a33e-26df-4412-abfe-b317845abf15" src="https://github.com/user-attachments/assets/7c01cecd-538d-413c-9938-12b3b7f63b7e" />


v)Image Rotation

```
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
<img width="471" height="354" alt="373127208-9c78a33e-26df-4412-abfe-b317845abf15" src="https://github.com/user-attachments/assets/79818b95-1025-4727-bd95-aaf34250f318" />


vi)Image Cropping

```
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```

<img width="494" height="364" alt="373126737-724b19af-be06-4de7-b090-4fa15ba754cf" src="https://github.com/user-attachments/assets/d49e21ab-513e-4ab9-a4ac-3023f7193fe5" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
