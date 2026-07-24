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

#### 1. Read the image ('supra.jpg') using OpenCV imread() as a grayscale image.
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("supra.webp",cv2.IMREAD_COLOR)
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
cv2.imwrite('supracar.webp',img)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img=cv2.imread('supracar.webp')
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

#### 9. Read in the image ('shajive.jpg').
```python
img2=cv2.imread('shajive.jpg',cv2.IMREAD_COLOR)
img2rgb=cv2.cvtColor(img2,cv2.COLOR_BGR2RGB)
plt.imshow(img2rgb)
```

#### 10. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
cv2.putText(img2rgb,"Shajive Kumar",(25,250),cv2.FONT_HERSHEY_SIMPLEX,1,(0,0,0),15)
cv2.putText(img2rgb,"Shajive Kumar",(25,250),cv2.FONT_HERSHEY_SIMPLEX,1,(255,255,255),2)
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

#### 13. Read the image ('supra.jpg').
```python
img=cv2.imread("supra.webp",cv2.IMREAD_COLOR)
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

<img width="1341" height="797" alt="Screenshot 2026-07-24 202036" src="https://github.com/user-attachments/assets/72606d73-3876-4603-ab60-6dd4aefcb803" />

<img width="1340" height="613" alt="Screenshot 2026-07-24 202052" src="https://github.com/user-attachments/assets/ba02d642-b6a9-4941-9e63-ab8d9db0e05a" />


<img width="1340" height="551" alt="Screenshot 2026-07-24 202104" src="https://github.com/user-attachments/assets/9a41dab4-5262-4d17-975b-8ec7dbcb248f" />

<img width="1335" height="590" alt="Screenshot 2026-07-24 202116" src="https://github.com/user-attachments/assets/4c84aed3-8e49-4ad8-bea4-c3c013016f50" />

<img width="1335" height="572" alt="Screenshot 2026-07-24 202126" src="https://github.com/user-attachments/assets/9998d800-3da6-4e1d-89cc-78f414b7768f" />


<img width="1333" height="600" alt="Screenshot 2026-07-24 202138" src="https://github.com/user-attachments/assets/820b60c8-9c91-4a7e-a890-3aefa7f0e6db" />

<img width="1337" height="601" alt="Screenshot 2026-07-24 202147" src="https://github.com/user-attachments/assets/6d451d79-eb42-4246-9ccf-d28a9d07c07f" />

<img width="1335" height="598" alt="Screenshot 2026-07-24 202155" src="https://github.com/user-attachments/assets/0b2257de-1ff6-4a12-848d-c5f2c8de9d44" />

<img width="1345" height="577" alt="Screenshot 2026-07-24 202203" src="https://github.com/user-attachments/assets/9cc497ac-f80b-4302-bf52-5a1d6ad908f0" />

<img width="1337" height="467" alt="Screenshot 2026-07-24 202213" src="https://github.com/user-attachments/assets/33469563-5da8-4b6e-b906-a9b95c7f58d2" />

<img width="1336" height="438" alt="Screenshot 2026-07-24 202221" src="https://github.com/user-attachments/assets/b6644bba-012d-4efd-a819-e9f49b8883d1" />

<img width="1338" height="441" alt="Screenshot 2026-07-24 202231" src="https://github.com/user-attachments/assets/23957422-3e37-46fc-b1ec-6bf321dd938d" />

<img width="1332" height="481" alt="Screenshot 2026-07-24 202242" src="https://github.com/user-attachments/assets/48460e95-21ab-4f65-8a71-30912486f0a0" />

<img width="1333" height="452" alt="Screenshot 2026-07-24 202253" src="https://github.com/user-attachments/assets/92b504f3-c9b1-4b38-af59-81c530967aa1" />

<img width="1337" height="721" alt="Screenshot 2026-07-24 202301" src="https://github.com/user-attachments/assets/406da1c8-dc84-493e-ae01-552493fe5250" />









## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

