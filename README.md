# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required libraries and image for transformation.

### Step2:
Perform operations on the image like translaton, rotation and other.

### Step3:
Use the warpPerspective(image , matrix, (rows, columns)) function.

### Step4:
Plot the Image and Transformed Image on the graph using matplotlib for identifying changes.

### Step5:
Diifferent operations has been performed on the image.

## Program:
### Developed By: Pabbarthi Chetan Sathish Kumar
### Register Number: 212220230033

## i)Image Translation
```python
import numpy as np
import matplotlib.pyplot as plt 
import cv2 as cv 

#plotting of an image 
image = cv.imread("ohm.jpg")
image = cv.cvtColor(image, cv.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(image)
plt.show()

#translation of an image 
rows,cols,dim = image.shape
M = np.float32([[1,0,100], [0,1,50],[0,0,1]])

translated_image= cv.warpPerspective(image, M, (cols, rows))

plt.axis("off")
plt.imshow(translated_image)
plt.show()
```
## ii) Image Scaling
```python
#SCALING 
rows,cols,dim = image.shape

M_scale = np.float32([[2,0,0], [0,1.6,0],[0,0,1]])

scale_image= cv.warpPerspective(image, M_scale, (cols, rows))


plt.axis("off")
plt.imshow(scale_image)
plt.show()
```

## iii)Image shearing
```python
#shearing image 
M_x = np.float32([[1,1,0], [0,1,0],[0,0,1]])

M_y = np.float32([[1,0,0], [0.4,1,0],[0,0,1]])


shear_imagex= cv.warpPerspective(image, M_x, (cols, rows))
shear_imagey= cv.warpPerspective(image, M_y, (cols, rows))


plt.axis("off")
plt.imshow(shear_imagex)
#plt.imshow(shear_imagey)
plt.show()


plt.axis("off")
#plt.imshow(shear_imagex)
plt.imshow(shear_imagey)
plt.show()
```

## iv)Image Reflection
```python
#reflect an image 
M_x = np.float32([[1,0,0],[0,-1,rows],[0,0,1]])

M_y = np.float32([[-1,0,cols], [0,1,0],[0,0,1]])

ref_imagex= cv.warpPerspective(image, M_x, (cols, rows))
ref_imagey= cv.warpPerspective(image, M_y, (cols, rows))


plt.axis("off")
plt.imshow(ref_imagex)
plt.show()


plt.axis("off")
plt.imshow(ref_imagey)
plt.show()
```

## v)Image Rotation
```python
angle=np.radians(10)
matrix=np.float32([[np.cos(angle),-np.sin(angle),0],
                                [np.sin(angle),np.cos(angle),0],
                                [0,0,1]])
Rotated_image=cv.warpPerspective(image,matrix,(cols,rows))
plt.axis("off")
plt.imshow(Rotated_image)
```

## vi)Image Cropping
```python
# cropping 
    
crop_img = image[600:750, 400:500]


plt.axis("off")
plt.imshow(crop_img)
plt.show()

```
## Output:
### i)Image Translation
![image](https://user-images.githubusercontent.com/74660507/166133116-04ca095a-b0d8-4bcc-9f08-f143cf42ada6.png)


### ii) Image Scaling
![image](https://user-images.githubusercontent.com/74660507/166133130-8ba51ee0-1ca6-4074-a731-cacafa4a1dbc.png)

### iii)Image shearing

![image](https://user-images.githubusercontent.com/74660507/166133147-c46d674c-ac6a-4f4a-9364-85ce8056fa40.png)


### iv)Image Reflection

![image](https://user-images.githubusercontent.com/74660507/166133163-97205fdd-675b-4745-9617-65faec501470.png)


### v)Image Rotation

![image](https://user-images.githubusercontent.com/74660507/166133179-1ec1bd65-97a8-4a7a-bb75-7fdef7c8a2d9.png)



### vi)Image Cropping
![image](https://user-images.githubusercontent.com/74660507/166133194-d451c312-b0a1-4b29-97a0-3c512db0f5e4.png)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
