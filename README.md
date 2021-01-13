# IpLab
1. Develop a program to display grayscale image using read and write operation.

Description: Grayscaling is the process of converting an image from other color spaces e.g RGB, CMYK, HSV, etc. to shades of gray. It varies between complete black and complete white.

Binary images are images whose pixels have only two possible intensity values. ... Binary images are often produced by thresholding a grayscale or color image, in order to separate an object in the image from the background. The color of the object (usually white) is referred to as the foreground color. to read an image we use the function cv2.imread(). to save a image we use cv2.imwrite(). to destroy all the windows(). 

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

 
import cv2 import numpy as np  
   
FILE_NAME = 'flower2.jpg' try:  
     
    # Read image from disk.  
     
    img = cv2.imread(FILE_NAME)     (height, width) = img.shape[:2]     cv2.imshow('gulaaaab.jpg', img)  
 
    res = cv2.resize(img, (int(width / 2), int(height / 2)), interpolation = cv2.INTER_CUBIC)      # Write image back to disk.     
 cv2.imshow('poooo.jpg', res)      
cv2.waitKey(0)    
except IOError:  
    print ('Error while reading files !!!') 


Output:

![image](https://user-images.githubusercontent.com/72368912/104433618-509cf200-55b0-11eb-8480-24c47dbe6f24.png)




