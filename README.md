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



