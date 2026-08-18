# Geometric Transformations Using OpenCV

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
** Name: Bharath K ** 

### Register No: 212224230036

---

##  Output
```PYTHON
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('baseball.jpg')  
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")  
plt.axis('off')
```
<img width="630" height="388" alt="image" src="https://github.com/user-attachments/assets/c239da72-bfe4-45f9-969f-c3f59765c813" />


### Image Translation
```
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0])) 
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Translated Image")  
plt.axis('off')
```

<img width="682" height="428" alt="image" src="https://github.com/user-attachments/assets/1c24f1a6-9bed-42a5-9628-deabdcbecb30" />


### Image Scaling
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB)) 
plt.title("Scaled Image")  
plt.axis('off')
```

<img width="735" height="222" alt="image" src="https://github.com/user-attachments/assets/cb3059e0-6b48-49f0-9531-ba56d79867a1" />


### Image Shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image")  
plt.axis('off')

```
<img width="702" height="415" alt="image" src="https://github.com/user-attachments/assets/f4b9c1ba-f363-4077-b512-9f3432cb4bd4" />


### Image Reflection
```
reflected_image = cv2.flip(image, 2)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  # Set title
plt.axis('off')
```

<img width="646" height="422" alt="image" src="https://github.com/user-attachments/assets/0de55f03-73f2-4dfc-b040-fad8fd453465" />


### Image Rotation
```
(height, width) = image.shape[:2]  
angle = 45  
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image") 
plt.axis('off')

```
<img width="722" height="400" alt="image" src="https://github.com/user-attachments/assets/62d955bd-4854-4dc0-af9e-4dd9ec438ef9" />

### Image Cropping
```
x, y, w, h = 100, 100, 200, 150  
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image") 
plt.axis('off')
```

<img width="687" height="482" alt="image" src="https://github.com/user-attachments/assets/358bab4b-7a4f-4ff4-b59d-26d1181ea83c" />


---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
