# Depth Image Estimation Project

This project involves estimating depth information from stereo images using various methods. It is organized into four problems, each employing different techniques to compute disparity maps.

## Table of Contents

1. [Problem 1: Pixel-wise Matching](#problem-1-pixel-wise-matching)
2. [Problem 2: Window-based Matching](#problem-2-window-based-matching)
3. [Problem 3: Window-based Matching with L1 and L2 Norms (Different Images)](#problem-3-window-based-matching-with-l1-and-l2-norms-different-images)
4. [Problem 4: Window-based Matching using Cosine Similarity](#problem-4-window-based-matching-using-cosine-similarity)

## Problem 1: Pixel-wise Matching

### 1. Download Dataset

```python
!gdown --id 14gf8bcym_lTcvjZQmg8kwq3aXkENBxMQ
!unzip tsukuba.zip -d tsukuba
```

### 2. Code
```python
import cv2
import numpy as np
from google.colab.patches import cv2_imshow

# Functions for distance calculations
def l1_distance(x, y):
    return abs(x - y)

def l2_distance(x, y):
    return (x - y) ** 2

# Paths to images
left_img_path = 'tsukuba/left.png'
right_img_path = 'tsukuba/right.png'
disparity_range = 16

# Read images
left = cv2.imread(left_img_path)
right = cv2.imread(right_img_path)

# Display images
cv2_imshow(left)
cv2_imshow(right)

# Pixel-wise matching using L1 distance
def pixel_wise_matching_l1(left_img, right_img, disparity_range, save_result=True):
    # Function implementation...
    pass

# Pixel-wise matching using L2 distance
def pixel_wise_matching_l2(left_img, right_img, disparity_range, save_result=True):
    # Function implementation...
    pass

# Run and display results
depth, color = pixel_wise_matching_l1(left_img_path, right_img_path, disparity_range, save_result=True)
cv2_imshow(depth)
cv2_imshow(color)

depth, color = pixel_wise_matching_l2(left_img_path, right_img_path, disparity_range, save_result=True)
cv2_imshow(depth)
cv2_imshow(color)
```

## Problem 2: Window-based matching.

### 1. Download Dataset

```python
!gdown --id 1wxmiUdqMciuTOs0ouKEISl8-iTVXdOWn
!unzip Aloe_images.zip
```

### 2. Code
```python
import cv2
import numpy as np
from google.colab.patches import cv2_imshow

# Functions for distance calculations
def l1_distance(x, y):
    return abs(x - y)

def l2_distance(x, y):
    return (x - y) ** 2

# Paths to images
left_img_path = 'Aloe/Aloe_left_1.png'
right_img_path = 'Aloe/Aloe_right_1.png'
disparity_range = 64
kernel_size = 3

# Read images
left = cv2.imread(left_img_path)
right = cv2.imread(right_img_path)

# Display images
cv2_imshow(left)
cv2_imshow(right)

# Window-based matching using L1 distance
def window_based_matching_l1(left_img, right_img, disparity_range, kernel_size=5, save_result=True):
    # Function implementation...
    pass

# Window-based matching using L2 distance
def window_based_matching_l2(left_img, right_img, disparity_range, kernel_size=5, save_result=True):
    # Function implementation...
    pass

# Run and display results
depth, color = window_based_matching_l1(left_img_path, right_img_path, disparity_range, kernel_size=kernel_size, save_result=True)
cv2_imshow(depth)
cv2_imshow(color)

depth, color = window_based_matching_l2(left_img_path, right_img_path, disparity_range, kernel_size=kernel_size, save_result=True)
cv2_imshow(depth)
cv2_imshow(color)
```

## Problem 3: Window-based Matching with L1 and L2 Norms (Different Images)
### 1. Download Dataset

```python
!gdown --id 1wxmiUdqMciuTOs0ouKEISl8-iTVXdOWn
!unzip Aloe_images.zip
```

### 2. Code
```python
import cv2
import numpy as np
from google.colab.patches import cv2_imshow

# Functions for distance calculations
def l1_distance(x, y):
    return abs(x - y)

def l2_distance(x, y):
    return (x - y) ** 2

# Paths to images
left_img_path = 'Aloe/Aloe_left_1.png'
right_img_path = 'Aloe/Aloe_right_2.png'
disparity_range = 64
kernel_size = 5

# Read images
left = cv2.imread(left_img_path)
right = cv2.imread(right_img_path)

# Display images
cv2_imshow(left)
cv2_imshow(right)

# Window-based matching using L1 distance
def window_based_matching_l1(left_img, right_img, disparity_range, kernel_size=5, save_result=True):
    # Function implementation...
    pass

# Window-based matching using L2 distance
def window_based_matching_l2(left_img, right_img, disparity_range, kernel_size=5, save_result=True):
    # Function implementation...
    pass

# Run and display results
depth, color = window_based_matching_l1(left_img_path, right_img_path, disparity_range, kernel_size=kernel_size, save_result=False)
cv2_imshow(depth)
cv2_imshow(color)

depth, color = window_based_matching_l2(left_img_path, right_img_path, disparity_range, kernel_size=kernel_size, save_result=False)
cv2_imshow(depth)
cv2_imshow(color)
```

## Problem 4: Window-based Matching using Cosine Similarity

### 1. Download Dataset

```python
!gdown --id 1wxmiUdqMciuTOs0ouKEISl8-iTVXdOWn
!unzip Aloe_images.zip
```

### 2. Code
```python
import cv2
import numpy as np
from google.colab.patches import cv2_imshow

# Function to compute cosine similarity
def cosine_similarity(x, y):
    numerator = np.dot(x, y)
    denominator = np.linalg.norm(x) * np.linalg.norm(y)
    return numerator / denominator

# Paths to images
left_img_path = 'Aloe/Aloe_left_1.png'
right_img_path = 'Aloe/Aloe_right_2.png'
disparity_range = 64
kernel_size = 5

# Read images
left = cv2.imread(left_img_path)
right = cv2.imread(right_img_path)

# Display images
cv2_imshow(left)
cv2_imshow(right)

# Window-based matching using cosine similarity
def window_based_matching(left_img, right_img, disparity_range, kernel_size=5, save_result=True):
    # Function implementation...
    pass

# Run and display results
depth, color = window_based_matching(left_img_path, right_img_path, disparity_range, kernel_size=kernel_size, save_result=False)
cv2_imshow(depth)
cv2_imshow(color)
```
## Notes

- **Make sure to have the required libraries installed:** OpenCV and NumPy.
- **Adjust file paths and parameters** according to your specific use case and dataset.
- **Results will be saved as images in the current directory** unless `save_result` is set to `False`.
# Additional Information

For any questions or issues, please open an issue in the repository or contact me at [truonghongkietcute@gmail.com](mailto:truonghongkietcute@gmail.com).

Feel free to customize the project names, descriptions, and any other details specific to your projects. If you encounter any problems or have suggestions for improvements, don't hesitate to reach out. Your feedback and contributions are welcome!

Let me know if there’s anything else you need or if you have any other questions. I’m here to help!
