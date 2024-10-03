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
Rotate the image using angle function.am:

Developed By:NITHYAA SRI S S

Register Number:212222230100
# Load the image
### Original image 
```


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('m.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Plot the original and transformed images
plt.figure(figsize=(12, 8))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')

````

![Screenshot 2024-10-03 154044](https://github.com/user-attachments/assets/30928e2e-b2ed-4e5c-9310-a081e6cc14d7)

### i)Image Translation
```

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
## Output:
![image](https://github.com/user-attachments/assets/a226b687-d2e0-400e-9823-3452caf49f32)
### ii) Image Scaling
```

scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
## Output:
![image](https://github.com/user-attachments/assets/9476d284-0dd2-4290-acd8-c5460d767ccd)

### iii)Image shearing
```

M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
## Output:
![image](https://github.com/user-attachments/assets/43a8341b-2674-4ff9-81ac-2cebc9a06ce8)

### iv)Image Reflection
```

reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
## Output:
![image](https://github.com/user-attachments/assets/3b2da3f5-4295-40c0-8925-d68da17ad106)

### v)Image Rotation
```

M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
plt.tight_layout()
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/2ec944fa-1fd2-4e23-b46a-de0d0800383e)
### vi)Image Cropping
# 6. Cropping
```
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
plt.figure(figsize=(17, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/7ce4cd16-3ae5-490b-9d11-8af3a2c5fc85)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
