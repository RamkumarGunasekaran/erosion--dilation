# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7  
2. OpenCV  

## Algorithm:
### Step1:
Import the necessary libraries (OpenCV, NumPy, Matplotlib).

### Step2:
Create a blank black image using NumPy and add text using `cv2.putText()`.

### Step3:
Create a 5x5 kernel (structuring element) using `np.ones()`.

### Step4:
Apply **erosion** using `cv2.erode()` to shrink white regions.

### Step5:
Apply **dilation** using `cv2.dilate()` to expand white regions.

 
## Program:

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline

def load_img():
    blank_img = np.zeros((600,600))
    font = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img, text='RAM', org=(50,300),
                fontFace=font, fontScale=5, color=(255,255,255),
                thickness=25, lineType=cv2.LINE_AA)
    return blank_img

def display_img(img):
    fig = plt.figure(figsize=(12,10))
    ax = fig.add_subplot(111)
    ax.imshow(img, cmap='gray')
    plt.show()

img = load_img()
display_img(img)

# Erosion
kernel = np.ones((5,5), dtype=np.uint8)
erosion1 = cv2.erode(img, kernel, iterations=3)
display_img(erosion1)

# Dilation
dilute = cv2.dilate(img, kernel, iterations=2)
display_img(dilute)
```
## Output:

### Display the Input Image
<img width="826" height="818" alt="c9e5d7b2-0f1e-482f-96f4-afe449c8db35" src="https://github.com/user-attachments/assets/a7f59272-2bcb-4dcf-b5ef-4dcd72fc22c3" />

### Display the Eroded Image
<img width="826" height="818" alt="76c33480-9cdc-4f92-b8cb-52cf86c148f5" src="https://github.com/user-attachments/assets/e7578376-ba3d-49fa-ab19-5944e1605454" />


### Display the Dilated Image
<img width="826" height="818" alt="32aac6cc-3cab-44fd-bba3-c240eafff517" src="https://github.com/user-attachments/assets/5fe342aa-b2e8-493a-aa3b-c07236964b45" />


## Result
Thus the generated text image is eroded and dilated using Python and OpenCV.
