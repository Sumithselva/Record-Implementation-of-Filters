# Record-Implementation-of-Filters
## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.
--- 

## Program

---

##  Developed By

- **Name:** SUMITH M
- **Register No:** 212224230279

---
### 1. Averaging Filter

```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Apply Averaging Filter
averaging = cv2.blur(img, (5, 5))

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(averaging)
plt.title("Averaging Filter")
plt.axis('off')

plt.show()

```

### 2. Weighted Averaging Filter

```

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Define Weighted Kernel
kernel = np.array([[1, 2, 1],
                   [2, 4, 2],
                   [1, 2, 1]], dtype=np.float32) / 16

# Apply Weighted Averaging
weighted = cv2.filter2D(img, -1, kernel)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis('off')

plt.show()

```

### 3. Gaussian Filter

```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Apply Gaussian Filter
gaussian = cv2.GaussianBlur(img, (5, 5), 0)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis('off')

plt.show()

```

### 4. Median Filter
```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Apply Median Filter
median = cv2.medianBlur(img, 5)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(median)
plt.title("Median Filter")
plt.axis('off')

plt.show()

```

### 5. Laplacian Sharpening Using Kernel

```

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Define Laplacian Kernel
kernel = np.array([[0, -1, 0],
                   [-1, 5, -1],
                   [0, -1, 0]])

# Apply Laplacian Sharpening
sharpened = cv2.filter2D(img, -1, kernel)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(sharpened)
plt.title("Laplacian Sharpening")
plt.axis('off')

plt.show()

```

### 6. Laplacian Operator

```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg', cv2.IMREAD_GRAYSCALE)

# Apply Laplacian Operator
laplacian = cv2.Laplacian(img, cv2.CV_64F)

# Convert to absolute values
laplacian = cv2.convertScaleAbs(laplacian)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img, cmap='gray')
plt.title("Original Grayscale Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')

plt.show()

```



##  Output

### Smoothing Filters

- Averaging filter produces blurred image  
<img width="971" height="281" alt="image" src="https://github.com/user-attachments/assets/3bf8f0fb-4df4-478c-a53e-6f613816a3fe" />



- Weighted averaging provides smoother result with less distortion
<img width="706" height="222" alt="image" src="https://github.com/user-attachments/assets/e8f267a7-ba05-453c-87fc-2e7d13a4e444" />



- Gaussian filter preserves edges better while reducing noise
- <img width="657" height="238" alt="image" src="https://github.com/user-attachments/assets/aa4b74e3-371d-4449-b968-cf4727ad1b9c" />



- Median filter removes salt-and-pepper noise effectively
- <img width="932" height="285" alt="image" src="https://github.com/user-attachments/assets/79c23f1d-1ae4-4125-b0d5-5c0f129bde0d" />




###  Sharpening Filters

- Laplacian kernel enhances edges and fine details
- <img width="727" height="251" alt="image" src="https://github.com/user-attachments/assets/c179b8fa-86fb-456c-b6d9-eadf28d9ff40" />



- Laplacian operator detects edges clearly in grayscale
- <img width="680" height="220" alt="image" src="https://github.com/user-attachments/assets/67035196-0a96-4059-8909-492c47621ba2" />

---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
