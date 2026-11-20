# Histogram-of-an-images

# **Name:** ABISHEK S

# **Register Number:** 212224240003


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

**Developed By:** ABISHEK S

**Register Number:** 212224240003

python

### Step1 : Histogram Equalization for Grayscale Images

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('image.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Step2 : Histogram Equalization for Color Images

```python
img = cv2.imread('eagle.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```




## Output

### Input Grayscale Image

<img width="361" height="434" alt="36a527b5-8d4a-455b-a438-3dd383bb42c8" src="https://github.com/user-attachments/assets/18120f37-3a57-4164-97a6-80172a2f6ca7" />


### Input Grayscale Image Range

<img width="579" height="434" alt="49d7c15e-da2d-4423-8199-8718807c8431" src="https://github.com/user-attachments/assets/ff5a1ad6-d8fe-41dd-985a-bcef2c8dd426" />


### Input Grayscale Image Equalized Histogram

<img width="579" height="434" alt="cba5b6a7-22bd-466f-a3ff-4d61409bf4ab" src="https://github.com/user-attachments/assets/62539f12-59aa-4094-bbb5-3a1e42de36d7" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="361" height="434" alt="cd8dce6e-fabc-487f-ba86-de25de81683f" src="https://github.com/user-attachments/assets/33d4746a-e47c-4c02-bde5-e49f030f8f9d" />


### Equalized Image

<img width="361" height="434" alt="616e984d-3654-488e-bca7-4212bf6c57fe" src="https://github.com/user-attachments/assets/b43dfbad-45e8-4cb1-805b-4a169dc932ee" />


### Equalized Histogram

<img width="547" height="434" alt="c1a81b9e-285f-499d-9b05-1d49269727e6" src="https://github.com/user-attachments/assets/debda4f9-5be3-4c8f-a58e-d318e262a035" />


### Final Output of Original Image and Equalized 

<img width="1202" height="414" alt="1e01b523-2893-485b-a95f-cdf998ad5c32" src="https://github.com/user-attachments/assets/4499f1f7-f9c1-4f88-8800-2d97b8b8026f" />


### Final Output of Original Image and its Histogram Equalized

<img width="1214" height="372" alt="5a7dfa9c-02a1-4f59-a504-a040c89483f2" src="https://github.com/user-attachments/assets/52e9d7ea-84bf-46c1-a141-566bde36ba65" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
