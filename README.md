# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---


### Developed By:
### Name: PRAHATHIESWARAN S
### Register No: 212225240107  



## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('profile.png', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```

<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/9f166b78-6d56-42b5-98f5-d1f30702fee5" />


```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/ed523f11-3e68-49ab-8230-47302eff1997" />
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="324" height="434" alt="image" src="https://github.com/user-attachments/assets/fffcd150-fdad-445b-a601-61c3c14dc159" />

## Histogram Equalization for Color Images


```
img = cv2.imread('profile.png', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```

<img width="324" height="434" alt="image" src="https://github.com/user-attachments/assets/d5531fe0-e1a2-4839-b9fc-878afd37998a" />

```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```

<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/790bb2db-48c9-49b8-9bb2-7f24a2bb1324" />

```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```

<img width="1157" height="414" alt="image" src="https://github.com/user-attachments/assets/f6c1f957-3743-4c77-b4c5-ca4a34920734" />

```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

<img width="1237" height="372" alt="image" src="https://github.com/user-attachments/assets/aea3d7ec-1c74-4ec5-9375-f9c1edee1e03" />


### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
