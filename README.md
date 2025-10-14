#  EXP-8: THRESHOLDING
# NAME: SARAVANAN SHAM PRAKASH
# REG NO: 212224230254
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program


# Load the necessary packages
```
import cv2
import matplotlib.pyplot as plt
```





# Read the Image and convert to grayscale
```
image=cv2.imread(r'C:\Users\admin\Desktop\DIPT\dipp img.jpg')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
```
# Original image
```
plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```


# Use Global thresholding to segment the image
```
_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)
```



# Use Adaptive thresholding to segment the image
```
adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```



# Use Otsu's method to segment the image 
```
_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

```
# Global Thresholding
```
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```
# Adaptive Thresholding
```
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```
# Otsu's Method
```
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```
# Show the plot
```
plt.tight_layout()
plt.show()

```
## Output

### Original Image
<img width="231" height="323" alt="image" src="https://github.com/user-attachments/assets/01966fe3-04b7-4ba2-b879-2a21701d16e3" />

### Global Thresholding
<img width="272" height="351" alt="image" src="https://github.com/user-attachments/assets/515cf4d7-679a-4114-b805-0bc741afbdfe" />


### Adaptive Thresholding
<img width="288" height="354" alt="image" src="https://github.com/user-attachments/assets/9a1ff4ff-666e-4029-a608-ca288379f0f6" />


### Optimum Global Thesholding using Otsu's Method
<img width="254" height="353" alt="image" src="https://github.com/user-attachments/assets/70e5e122-b204-436d-a603-04d57db5d522" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
