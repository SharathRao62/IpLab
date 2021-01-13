# IpLab
1. Develop a program to display grayscale image using read and write operation.

Description:

program:
import cv2 
image=cv2.imread('flower2.jpg') cv2.imshow('Original',image) 
cv2.waitKey(0) gray_image=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imwrite('flower1.jpg',gray_image)
cv2.imshow('Grayscale',gray_image)
cv2.waitKey(0) 
cv2.destroyAllWindows() 

Output:

![image](https://user-images.githubusercontent.com/72368912/104432190-c607c300-55ae-11eb-9a49-56d225c04eec.png)

2) Develop a program to perform linear transformations on an image: Scaling and Rotation



a)Scaling
 
import cv2 import numpy as np  
   
FILE_NAME = 'flower2.jpg' try:  
     
    # Read image from disk.  
     
   img = cv2.imread(FILE_NAME)     
   (height, width) = img.shape[:2]     
   cv2.imshow('gulaaaab.jpg', img)  
 
   res = cv2.resize(img, (int(width / 2), int(height / 2)), interpolation = cv2.INTER_CUBIC)      
   # Write image back to disk.     
 cv2.imshow('poooo.jpg', res)      
cv2.waitKey(0)    
except IOError:  
    print ('Error while reading files !!!') 


Output:

![image](https://user-images.githubusercontent.com/72368912/104433618-509cf200-55b0-11eb-8480-24c47dbe6f24.png)

b)Rotation

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


3.Develop a program to find the sum and mean of a set of images. Create ‘n’ number of images and read them from the directory and perform the operations.

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


4 Develop a program to convert the color image to gray scale and binary image.

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

5 Develop a program to convert the given color image to different color spaces

import cv2 
image=cv2.imread('flower2.jpg') cv2.imshow('Original',image) 
cv2.waitKey(0) color_space1=cv2.cvtColor(image,cv2.COLOR_BGR2RGB) cv2.imshow('RGB',color_space1)
cv2.waitKey(0) 
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


6.Develop a program to create an image from 2D array (generate an array of random size).

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



