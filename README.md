# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** SABEESHWARAN  
- **Register Number:** 212225230234

  ### Ex. No. 01

#### 1. Read the image ('vijay.jpg') using OpenCV imread() as a grayscale image.
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("vijay.webp",cv2.IMREAD_COLOR)
img_rgb=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
img_gray=cv2.cvtColor(img_rgb,cv2.COLOR_RGB2GRAY)
```

#### 2. Print the image width, height & Channel.
```python
img.shape
```

#### 3. Display the image using matplotlib imshow().
```python
plt.imshow(img_rgb)
plt.imshow(img_gray,cmap='gray')
```

#### 4. Save the image file using OpenCV imwrite().
```python
cv2.imwrite('vijaytrisha.webp',img)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img=cv2.imread('vijaytrisha.webp')
```


#### 6. Crop the image to extract any specific object from the image.
```python
crop=img_rgb[50:500,550:900]
plt.imshow(crop)
```

#### 7. Resize the image up by a factor of 2x.
```python
res=cv2.resize(crop,(800,900))
plt.imshow(res)
```

#### 8. Flip the cropped/resized image horizontally.
```python
flip=cv2.flip(res,1)
plt.imshow(flip)
```

#### 9. Read in the image ('stalin.jpg').
```python
img2=cv2.imread('stalin.jpg',cv2.IMREAD_COLOR)
img2rgb=cv2.cvtColor(img2,cv2.COLOR_BGR2RGB)
plt.imshow(img2rgb)
```

#### 10. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
cv2.putText(img2rgb,"Former Chief Minister",(25,250),cv2.FONT_HERSHEY_SIMPLEX,1,(0,0,0),15)
cv2.putText(img2rgb,"Former Chief Minister",(25,250),cv2.FONT_HERSHEY_SIMPLEX,1,(255,255,255),2)
plt.imshow(img2rgb)
```

#### 11. Draw a rectangle that encompasses the launch tower and the rocket.
```python
rect=cv2.rectangle(img3rgb,(300,25),(100,400),(255,255,255),5)
```

#### 12. Display the final annotated image.
```python
plt.imshow(rect)
```

#### 13. Read the image ('vijay.jpg').
```python
img=cv2.imread("vijay.webp",cv2.IMREAD_COLOR)
img_rgb=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
```

#### 14. Adjust the brightness of the image.
```python
m = np.ones(img_rgb.shape, dtype="uint8") * 50
bright = cv2.add(img_rgb, m)
plt.imshow(bright)
```

#### 15. Modify the image contrast.
```python
contrast = cv2.convertScaleAbs(img_rgb, alpha=1.2, beta=0)
plt.imshow(contrast)
```

#### 16. Split the image into the B,G,R components & Display the channels.
```python
b,g,r=cv2.split(img)
plt.imshow(b)
plt.imshow(g)
plt.imshow(r)
```

#### 17. Merged the R, G, B , displays along with the original image
```python
merged = cv2.merge([r, g, b])

plt.imshow(merged)

```

#### 18. Split the image into the H, S, V components & Display the channels.
```python
h, s, v = cv2.split(hsv)
```
#### 19. Merged the H, S, V, displays along with original image.
```python
merged_hsv = cv2.merge([h, s, v])
```

## Output:
- **i)** Read and Display an Image.
- <img width="552" height="379" alt="download" src="https://github.com/user-attachments/assets/dc7bcd5b-bb9c-47fd-82d4-eb26bf4c21e0" />
  
- **ii)** Adjust Image Brightness.
- <img width="552" height="379" alt="download" src="https://github.com/user-attachments/assets/6a0fb006-b15e-4091-8e4f-59838852eeb0" />
  
- **iii)** Modify Image Contrast.
- <img width="552" height="379" alt="download" src="https://github.com/user-attachments/assets/6a8e02cc-715e-4bef-a812-c9888a0e1e85" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

