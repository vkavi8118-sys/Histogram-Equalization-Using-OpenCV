## EXP. NO: 03
# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** KAVINAYA V

**Register Number:** 212225230133

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image
<img width="817" height="642" alt="Screenshot 2026-10-25 151247" src="https://github.com/user-attachments/assets/50243560-1724-48d1-954b-443e8078ab36" />

### Input Grayscale Image Range
<img width="851" height="643" alt="Screenshot 2026-10-25 151307" src="https://github.com/user-attachments/assets/6d8a00a7-619a-44ae-93aa-ce5b3d3439ae" />

### Input Grayscale Image Equalized Histogram
<img width="851" height="643" alt="Screenshot 2026-10-25 151320" src="https://github.com/user-attachments/assets/9a25d3f2-c9c1-4a7e-9327-1bf15886219d" />


### Histogram of Grayscale Image and Color Image Channels
### Original Image
<img width="820" height="647" alt="Screenshot 2026-10-25 151327" src="https://github.com/user-attachments/assets/20298b55-71c4-4e42-8edd-66c8073519ed" />

### Equalized Image
<img width="817" height="648" alt="Screenshot 2026-10-25 151343" src="https://github.com/user-attachments/assets/165ec403-4f67-4f8e-9b94-e1ad57b7f17e" />

### Equalized Histogram
<img width="851" height="645" alt="Screenshot 2026-10-25 151423" src="https://github.com/user-attachments/assets/10693f2e-c99d-49aa-8165-ee2be207aa4d" />

### Final Output of Original Image and Equalized 
<img width="1635" height="490" alt="Screenshot 2026-10-25 151439" src="https://github.com/user-attachments/assets/acc43210-c6b3-452d-b197-30fdd50c48f5" />

### Final Output of Original Image and its Histogram Equalized
<img width="1636" height="488" alt="Screenshot 2026-10-25 151449" src="https://github.com/user-attachments/assets/db5c8d41-43f5-4b0a-88e9-3c698a03a54d" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
