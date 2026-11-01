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

**Developed By:** SABEEHA PARVEEN K

**Register Number:** 212225230233

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

<img width="437" height="487" alt="image" src="https://github.com/user-attachments/assets/def9f440-93c1-4426-bb1f-f8f180c0248b" />

### Input Grayscale Image Range

<img width="752" height="502" alt="image" src="https://github.com/user-attachments/assets/26ccb695-0f43-461c-b67b-8f464e8b5fca" />

### Input Grayscale Image Equalized Histogram

<img width="772" height="487" alt="image" src="https://github.com/user-attachments/assets/0c84a9e9-c089-4e7b-b7d1-163b962fd1b0" />

### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="441" height="491" alt="image" src="https://github.com/user-attachments/assets/6591d429-85f4-4244-ba26-9a0077e279bc" />

### Equalized Image

<img width="451" height="492" alt="image" src="https://github.com/user-attachments/assets/5e832441-61f0-4e98-aca1-32ab722bb8c6" />

### Equalized Histogram

<img width="710" height="492" alt="image" src="https://github.com/user-attachments/assets/1bef54e4-f4e9-454d-aab8-150ec00de2eb" />

### Final Output of Original Image and Equalized 

<img width="1257" height="430" alt="image" src="https://github.com/user-attachments/assets/311ef7b7-1f88-4ae9-8209-36623091caba" />

### Final Output of Original Image and its Histogram Equalized

<img width="1242" height="367" alt="image" src="https://github.com/user-attachments/assets/76a08483-1d4a-4abf-8aed-680a80c30d5e" />

## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
