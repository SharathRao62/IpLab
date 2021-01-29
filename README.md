# IpLab
# 1) Develop a program to display grayscale image using read and write operation.

Description: Grayscaling is the process of converting an image from other color spaces e.g RGB, CMYK, HSV, etc. to shades of gray. It varies between complete black and complete white.
Using OpenCV : OpenCV (Open Source Computer Vision) is a computer vision library that contains various functions to perform operations on pictures or videos. It was originally developed by Intel but was later maintained by Willow Garage and is now maintained by Itseez. This library is cross-platform that is it is available on multiple programming languages such as Python, C++ etc.

Program:

```python
import cv2
image=cv2.imread('flower2.jpg')
cv2.imshow('Original',image) 
cv2.waitKey(0) 
gray_image=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imwrite('flower1.jpg',gray_image)
cv2.imshow('Grayscale',gray_image)
cv2.waitKey(0) 
cv2.destroyAllWindows() 
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/104432190-c607c300-55ae-11eb-9a49-56d225c04eec.png)


# 2) Develop a program to perform linear transformations on an image: Scaling and Rotation

Description: Linear Transformation is type of gray level transformation that is used for image enhancement. It is a spatial domain method. It is used for manipulation of an image so that the result is more suitable than the original for a specific application

# a) Scaling
Description: Scaling operation increases/reduces size of an image.

Program:
```python
import cv2 import numpy as np  
FILE_NAME = 'flower2.jpg' try:    
img = cv2.imread(FILE_NAME)  
(height, width) = img.shape[:2]  
cv2.imshow('gulaaaab.jpg', img)  
res = cv2.resize(img, (int(width / 2), int(height / 2)), interpolation = cv2.INTER_CUBIC)      
cv2.imshow('poooo.jpg', res)     
cv2.waitKey(0)    
except IOError:  
print ('Error while reading files !!!') 
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/104433618-509cf200-55b0-11eb-8480-24c47dbe6f24.png)

# b) Rotation
Description: Images can be rotated to any degree clockwise or otherwise. We just need to define rotation matrix listing rotation point, degree of rotation and the scaling factor.

Program:
```python
import cv2 import numpy as np  
FILE_NAME = 'flower2.jpg' 
try:  
img = cv2.imread(FILE_NAME)  
(rows, cols) = img.shape[:2]
cv2.imshow('gulaaaab.jpg', img)  
M = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)   
res = cv2.warpAffine(img, M, (cols, rows))  
cv2.imshow('result.jpg', res)    
cv2.waitKey(0)  except IOError:  
print ('Error while reading files !!!') 
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/104434051-c7d28600-55b0-11eb-8f14-a456658a5760.png)


# 3) Develop a program to find the sum and mean of a set of images. Create ‘n’ number of images and read them from the directory and perform the operations.
Description: Mean is most basic of all statistical measure. Means are often used in geometry and analysis; a wide range of means have been developed for these purposes. In contest of image processing filtering using mean is classified as spatial filtering and used for noise reduction.

Program:

```python
import cv2
import os
path='D:\Sharath\imagesip'
imgs = []
files= os.listdir(path)
for file in files:
fpat=path+"\\"+file
imgs.append(cv2.imread(fpat)) 
i=0
for im in imgs:            
#for i in range(len(files)):
cv2.imshow(files[i],imgs[i])  
i=i+1;
cv2.imshow('mean',im/i)
mean=(im/i)
print(mean)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

***Output:***


![image](https://user-images.githubusercontent.com/72368912/104435117-03ba1b00-55b2-11eb-97ae-495cc3f69357.png)


# 4) Develop a program to convert the color image to gray scale and binary image.

Description:
Types of an image
BINARY IMAGE– The binary image as its name suggests, contain only two pixel elements i.e 0 & 1,where 0 refers to black and 1 refers to white. This image is also known as Monochrome.
BLACK AND WHITE IMAGE– The image which consist of only black and white color is called BLACK AND WHITE IMAGE.
8 bit COLOR FORMAT– It is the most famous image format.It has 256 different shades of colors in it and commonly known as Grayscale Image. In this format, 0 stands for Black, and 255 stands for white, and 127 stands for gray.
16 bit COLOR FORMAT– It is a color image format. It has 65,536 different colors in it.It is also known as High Color Format. In this format the distribution of color is not as same as Grayscale image.

Program:

```python
import cv2
image=cv2.imread('flower2.jpg')
cv2.imshow('Original',image)
cv2.waitKey(0) 
gray_image=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow('Grayscale',gray_image) 
cv2.waitKey(0) 
sqr,binary_image=cv2.threshold(gray_image,172,240,cv2.THRESH_BINARY) 
cv2.imshow('BinaryImage',binary_image) 
cv2.waitKey(0)
cv2.destroyAllWindows() 
```

***Output:***


![image](https://user-images.githubusercontent.com/72368912/104435739-bc805a00-55b2-11eb-9607-98cdd7abc5e5.png)


# 5) Develop a program to convert the given color image to different color spaces

Description:
Color spaces are a way to represent the color channels present in the image that gives the image that particular hue. There are several different color spaces and each has its own significance.
Some of the popular color spaces are RGB (Red, Green, Blue), CMYK (Cyan, Magenta, Yellow, Black), HSV (Hue, Saturation, Value), etc.

BGR color space: OpenCV’s default color space is RGB. However, it actually stores color in the BGR format. It is an additive color model where the different intensities of Blue, Green and Red give different shades of color.

HSV color space: It stores color information in a cylindrical representation of RGB color points. It attempts to depict the colors as perceived by the human eye. Hue value varies from 0-179, Saturation value varies from 0-255 and Value value varies from 0-255. It is mostly used for color segmentation purpose.


Program:

```python
import cv2
image=cv2.imread('flower2.jpg')
cv2.imshow('Original',image)
cv2.waitKey(0)
color_space1=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
cv2.imshow('RGB',color_space1)
cv2.waitKey(0)
color_space2=cv2.cvtColor(image,cv2.COLOR_BGR2HSV)
cv2.imshow('HSV',color_space2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/104436325-77a8f300-55b3-11eb-9caf-2479c4e298ce.png)


# 6) Develop a program to create an image from 2D array (generate an array of random size).

Description:
Two dimensional array is an array within an array. It is an array of arrays. In this type of array the position of an data element is referred by two indices instead of one. So it represents a table with rows an dcolumns of data.

Program:
```python
import numpy, cv2
img=numpy.zeros([200,200,3])
img[:,:,0]=numpy.ones([200,200])*255
img[:,:,1]=numpy.ones([200,200])*255
img[:,:,2]=numpy.ones([200,200])*0
cv2.imwrite('flower1.jpg',img)
cv2.imshow('Color image',img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/104437041-54cb0e80-55b4-11eb-877d-971eb6d6ec63.png)

# 7) Find the Neighbourhood Matrix

Description:
A pixel's neighborhood is some set of pixels, defined by their locations relative to that pixel, which is called the center pixel. The neighborhood is a rectangular block, and as you move from one element to the next in an image matrix, the neighborhood block slides in the same direction.

Program:
```python
import numpy as np
axis = 3
x =np.empty((axis,axis))
y = np.empty((axis+2,axis+2))
s =np.empty((axis,axis))
x = np.array([[1,4,3],[2,8,5],[3,4,6]])
print('matrix\n')
for i in range(0,axis):
for j in range(0,axis):
print(int(x[i][j]),end = '\t')
print('\n')
print('Temp matrix\n')
for i in range(0,axis+2):
for j in range(0,axis+2):
if i == 0 or i == axis+1 or j == 0 or j==axis+1:
y[i][j]=0
else:
#print("i = {}, J = {}".format(i,j))
y[i][j]=x[i-1][j-1]
for i in range(0,axis+2):
for j in range(0,axis+2):
print(int(y[i][j]),end = '\t')
print('\n')
```


***Output:***

![image](https://user-images.githubusercontent.com/72368912/104444143-65cc4d80-55bd-11eb-8eae-a79e71e17a84.png)


# 8) Calculate the Neighbourhood of Matrix

Description:
Given a M x N matrix, find sum of all K x K sub-matrix 2. Given a M x N matrix and a cell (i, j), find sum of all elements of the matrix in constant time except the elements present at row i & column j of the matrix. Given a M x N matrix, calculate maximum sum submatrix of size k x k in a given M x N matrix in O (M*N) time. Here, 0 < k < M, N.

Program:
```Python
import numpy as np
axis = 3
x =np.empty((axis,axis)) np.empty((axis+2,axis+2))
r=np.empty((axis,axis))s =np.empty((axis,axis))
x = np.array([[1,4,3],[2,8,5],[3,4,6]])
print('Matrix\n')for i in range(0,axis):
for j in range(0,:
print(int(x[i][j]),end = '\t')
print('\n')
print('Temp matrix\n')
for i in range(0,axis+2):
for j in range(0,axis+2):
if i == 0 or i == axis+1 or j == 0 or j==axis+1:
y[i][j]=0
else:
 #print("i = {}, J = {}".format(i,j))
y[i][j]=x[i-1][j-1]  
for i in range(0,axis+2):
for j in range(0,axis+2):
print(int(y[i][j]),end = '\t')
print('\n')
print('Output calculated Neighbours of matrix\n')
print('sum of Neighbours of matrix\n')
for i in range(0,axis):
for j in range(0,axis):    
r[i][j]=((y[i][j]+y[i][j+1]+y[i][j+2]+y[i+1][j]+y[i+1][j+2]+y[i+2][j]+y[i+2][j+1]+y[i+2][j+2]))
print(r[i][j],end = '\t')
print('\n')
print('\n Average of Neighbours of matrix\n')
for i in range(0,axis):
for j in range(0,axis):   
s[i][j]=((y[i][j]+y[i][j+1]+y[i][j+2]+y[i+1][j]+y[i+1][j+2]+y[i+2][j]+y[i+2][j+1]+y[i+2][j+2])/8)
print(s[i][j],end = '\t')
print('\n')
```  

***Output:***

![image](https://user-images.githubusercontent.com/72368912/104446136-0459ae00-55c0-11eb-8b76-ea78c7b3b8da.png)

![image](https://user-images.githubusercontent.com/72368912/104446262-33701f80-55c0-11eb-816e-052f375365a8.png)

# 9) Develop a program to implement Negative Transformation of a image

Description:The second linear transformation is negative transformation, which is invert of identity transformation. In negative transformation, each value of the input image is subtracted from the L-1 and mapped onto the output image.

Program:
```python
import cv2 
import matplotlib.pyplot as plt
img_Original = cv2.imread('flower2.jpg', 1) 
plt.imshow(img_Original) 
plt.show() 
cv2.waitKey(0)
img_neg = 255 - img_Original 
plt.imshow(img_neg) 
plt.show() 
cv2.waitKey(0)
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/105327249-aeef5380-5bf4-11eb-9a18-87a5397ad295.png)

# Contrast

Description: Contrast can be simply explained as the difference between maximum and minimum pixel intensity in an image.

Program:
```python
from PIL import Image, ImageEnhance
img = Image.open("flower2.jpg")
img.show()
img=ImageEnhance.Color(img)
img.enhance(2.0).show()
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/105328282-e4487100-5bf5-11eb-9205-9ae98a107fca.png)

![image](https://user-images.githubusercontent.com/72368912/105328385-ff1ae580-5bf5-11eb-81c6-bc6418233bd4.png)


# Thresholding Brightness

Description: Brightness is a relative term. It depends on your visual perception. Since brightness is a relative term, so brightness can be defined as the amount of energy output by a source of light relative to the source we are comparing it to. In some cases we can easily say that the image is bright, and in some cases, its not easy to perceive.

Program:
```python
import cv2  
import numpy as np  

image1 = cv2.imread('flower2.jpg')  

img = cv2.cvtColor(image1, cv2.COLOR_BGR2GRAY)
 
ret, thresh1 = cv2.threshold(img, 120, 255, cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(img, 120, 255, cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(img, 120, 255, cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(img, 120, 255, cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(img, 120, 255, cv2.THRESH_TOZERO_INV)

cv2.imshow('Binary Threshold', thresh1)
cv2.imshow('Binary Threshold Inverted', thresh2)
cv2.imshow('Truncated Threshold', thresh3)
cv2.imshow('Set to 0', thresh4)
cv2.imshow('Set to 0 Inverted', thresh5)

if cv2.waitKey(0) & 0xff == 27:  
   cv2.destroyAllWindows() 
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/105328576-3093b100-5bf6-11eb-9d0e-d44d6c975558.png)

![image](https://user-images.githubusercontent.com/72368912/105328646-44d7ae00-5bf6-11eb-8ec0-83ec1da71826.png)

![image](https://user-images.githubusercontent.com/72368912/105328742-60db4f80-5bf6-11eb-85b8-dab203058434.png)

![image](https://user-images.githubusercontent.com/72368912/105328799-72245c00-5bf6-11eb-9945-957f30adde53.png)

![image](https://user-images.githubusercontent.com/72368912/105328866-823c3b80-5bf6-11eb-9bf6-5a2f0106ea5b.png)



# 10) Develop a program to implement Power Law Transformation

Description: There are further two transformation is power law transformations, that include nth power and nth root transformation. These transformations can be given by the expression:

s=cr^γ

This symbol γ is called gamma, due to which this transformation is also known as gamma transformation.

Variation in the value of γ varies the enhancement of the images. Different display devices / monitors have their own gamma correction, that’s why they display their image at different intensity.

This type of transformation is used for enhancing images for different type of display devices. The gamma of different display devices is different. For example Gamma of CRT lies in between of 1.8 to 2.5, that means the image displayed on CRT is dark.

Correcting gamma. s=cr^γ

s=cr^(1/2.5)

Program:
```python
import numpy as np
import cv2
img = cv2.imread('flower2.jpg')
gamma_two_point_two = np.array(255*(img/255)**2.2,dtype='uint8')
gamma_point_four = np.array(255*(img/255)**0.4,dtype='uint8')
img3 = cv2.hconcat([gamma_two_point_two,gamma_point_four])
cv2.imshow('a2',img3)
cv2.waitKey(0)
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/105329055-bca5d880-5bf6-11eb-986d-0331651d7ac3.png)



# 11) Develop program to display  Histogram of an image

Description: A histogram is a graph. A graph that shows frequency of anything. Usually histogram have bars that represent frequency of occurring of data in the whole data set. A Histogram has two axis the x axis and the y axis. The x axis contains event whose frequency you have to count. The y axis contains frequency. The different heights of bar shows different frequency of occurrence of data. Histogram of an image, like other histograms also shows frequency. But an image histogram, shows frequency of pixels intensity values. In an image histogram, the x axis shows the gray level intensities and the y axis shows the frequency of these intensities.

Program:
```python
import cv2
from matplotlib import pyplot as plt
img = cv2.imread('flower2.jpg',0)
histr = cv2.calcHist([img],[0],None,[256],[0,256])
plt.plot(histr)
plt.show()
```

***Output:***

![image](https://user-images.githubusercontent.com/72368912/105329195-e4953c00-5bf6-11eb-96fc-00031e0be8b4.png)

