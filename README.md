# IpLab
# 1) Develop a program to display grayscale image using read and write operation.

Description: Grayscaling is the process of converting an image from other color spaces e.g RGB, CMYK, HSV, etc. to shades of gray. It varies between complete black and complete white.
Using OpenCV : OpenCV (Open Source Computer Vision) is a computer vision library that contains various functions to perform operations on pictures or videos. It was originally developed by Intel but was later maintained by Willow Garage and is now maintained by Itseez. This library is cross-platform that is it is available on multiple programming languages such as Python, C++ etc.

Program:

import cv2
image=cv2.imread('flower2.jpg') 
cv2.imshow('Original',image) 
cv2.waitKey(0) 
gray_image=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imwrite('flower1.jpg',gray_image)
cv2.imshow('Grayscale',gray_image)
cv2.waitKey(0) 
cv2.destroyAllWindows() 

Output:

![image](https://user-images.githubusercontent.com/72368912/104432190-c607c300-55ae-11eb-9a49-56d225c04eec.png)

# 2) Develop a program to perform linear transformations on an image: Scaling and Rotation

Description: Linear Transformation is type of gray level transformation that is used for image enhancement. It is a spatial domain method. It is used for manipulation of an image so that the result is more suitable than the original for a specific application

# a) Scaling
Description: Scaling operation increases/reduces size of an image.

Program:
import cv2 import numpy as np  
   
FILE_NAME = 'flower2.jpg' try:  
     
    # Read image from disk.  
     
img = cv2.imread(FILE_NAME)     
(height, width) = img.shape[:2]     
cv2.imshow('gulaaaab.jpg', img)  
 
res = cv2.resize(img, (int(width / 2), int(height / 2)), interpolation = cv2.INTER_CUBIC)      
#Write image back to disk.     
cv2.imshow('poooo.jpg', res)      
cv2.waitKey(0)    
except IOError:  
print ('Error while reading files !!!') 


Output:

![image](https://user-images.githubusercontent.com/72368912/104433618-509cf200-55b0-11eb-8480-24c47dbe6f24.png)

# b) Rotation
Description: Images can be rotated to any degree clockwise or otherwise. We just need to define rotation matrix listing rotation point, degree of rotation and the scaling factor.

Program:

import cv2 import numpy as np  
   
FILE_NAME = 'flower2.jpg' 
try:  
img = cv2.imread(FILE_NAME)  
(rows, cols) = img.shape[:2]
cv2.imshow('gulaaaab.jpg', img)  
   
M = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)    
res = cv2.warpAffine(img, M, (cols, rows))  
   
cv2.imshow('result.jpg', res)      cv2.waitKey(0)  except IOError:  
print ('Error while reading files !!!') 


Output:

![image](https://user-images.githubusercontent.com/72368912/104434051-c7d28600-55b0-11eb-8f14-a456658a5760.png)


# 3) Develop a program to find the sum and mean of a set of images. Create ‘n’ number of images and read them from the directory and perform the operations.
Description: Mean is most basic of all statistical measure. Means are often used in geometry and analysis; a wide range of means have been developed for these purposes. In contest of image processing filtering using mean is classified as spatial filtering and used for noise reduction.

Program:
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
#cv2.destroyAllWindows()

Output:


![image](https://user-images.githubusercontent.com/72368912/104435117-03ba1b00-55b2-11eb-97ae-495cc3f69357.png)


# 4) Develop a program to convert the color image to gray scale and binary image.

Description:
Types of an image
BINARY IMAGE– The binary image as its name suggests, contain only two pixel elements i.e 0 & 1,where 0 refers to black and 1 refers to white. This image is also known as Monochrome.
BLACK AND WHITE IMAGE– The image which consist of only black and white color is called BLACK AND WHITE IMAGE.
8 bit COLOR FORMAT– It is the most famous image format.It has 256 different shades of colors in it and commonly known as Grayscale Image. In this format, 0 stands for Black, and 255 stands for white, and 127 stands for gray.
16 bit COLOR FORMAT– It is a color image format. It has 65,536 different colors in it.It is also known as High Color Format. In this format the distribution of color is not as same as Grayscale image.

Program:
import cv2
image=cv2.imread('flower2.jpg')
cv2.imshow('Original',image)
cv2.waitKey(0) 
gray_image=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow('Grayscale',gray_image) 
cv2.waitKey(0) 
sqr,binary_image=cv2.threshold(gray_image,172,240,cv2.THRESH_BINARY) 
cv2.imshow('BinaryImage',binary_image) 
cv2.waitKey(0) cv2.destroyAllWindows() 

Output:


![image](https://user-images.githubusercontent.com/72368912/104435739-bc805a00-55b2-11eb-9607-98cdd7abc5e5.png)

# 5) Develop a program to convert the given color image to different color spaces

Description:
Color spaces are a way to represent the color channels present in the image that gives the image that particular hue. There are several different color spaces and each has its own significance.
Some of the popular color spaces are RGB (Red, Green, Blue), CMYK (Cyan, Magenta, Yellow, Black), HSV (Hue, Saturation, Value), etc.

BGR color space: OpenCV’s default color space is RGB. However, it actually stores color in the BGR format. It is an additive color model where the different intensities of Blue, Green and Red give different shades of color.

HSV color space: It stores color information in a cylindrical representation of RGB color points. It attempts to depict the colors as perceived by the human eye. Hue value varies from 0-179, Saturation value varies from 0-255 and Value value varies from 0-255. It is mostly used for color segmentation purpose.


Program:

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


Output:

![image](https://user-images.githubusercontent.com/72368912/104436325-77a8f300-55b3-11eb-9caf-2479c4e298ce.png)


# 6) Develop a program to create an image from 2D array (generate an array of random size).

Description:
Two dimensional array is an array within an array. It is an array of arrays. In this type of array the position of an data element is referred by two indices instead of one. So it represents a table with rows an dcolumns of data.

Program:

import numpy, cv2
img=numpy.zeros([200,200,3])

img[:,:,0]=numpy.ones([200,200])*255
img[:,:,1]=numpy.ones([200,200])*255
img[:,:,2]=numpy.ones([200,200])*0

cv2.imwrite('flower1.jpg',img)
cv2.imshow('Color image',img)

cv2.waitKey(0)
cv2.destroyAllWindows()

Output:

![image](https://user-images.githubusercontent.com/72368912/104437041-54cb0e80-55b4-11eb-877d-971eb6d6ec63.png)



