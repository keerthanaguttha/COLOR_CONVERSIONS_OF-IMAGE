# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: Guttha Keerthana
### Register Number: 212223240045


## Output:

### i) Read and display the image

import cv2
image=cv2.imread('1.JPEG')
image=cv2.resize(image,(400,400))
cv2.imshow('1',image)
cv2.waitKey(0)
cv2.destroyAllWindows


## Output:
![image](https://github.com/user-attachments/assets/7143e256-9bb5-4106-895b-e134bcb7dd75)

### ii)Write the image

image=cv2.imread('1.JPEG',0)
cv2.imwrite('2.JPEG',image)

## Output:
![image](https://github.com/user-attachments/assets/3cae2959-e13f-4598-8eee-b37e028d9dee)


### iii)Shape of the Image

import cv2
image=cv2.imread('1.JPEG')
print(image.shape)

## Output:
![image](https://github.com/user-attachments/assets/62d005fa-3432-4e0b-901e-1603da56bb6b)


### iv)Access rows and columns

import random
import cv2
image=cv2.imread('1.JPEG',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                   random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('panda image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()


## Output:
![image](https://github.com/user-attachments/assets/3e6c386e-57a0-429f-b53b-5d9ff5c274f0)


### v)Cut and paste portion of image

import cv2
image=cv2.imread('1.JPEG')
image=cv2.resize(image,(400,400))
tag =image[130:200,110:190]
image[110:180,120:200] = tag
cv2.imshow('cut and paste',image)
cv2.waitKey(0)
cv2.destroyAllWindows()


## Output:
![image](https://github.com/user-attachments/assets/191fd84f-86e0-4aa1-807c-6bc4ff3cc281)
 

### vi) BGR and RGB to HSV and GRAY

import cv2
img = cv2.imread('1.JPEG')
img = cv2.resize(img,(300,300))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()

## Output:
![image](https://github.com/user-attachments/assets/427e2eb7-0d18-40be-86e0-c8820bbcd780)
![image](https://github.com/user-attachments/assets/00de67ad-8d38-494f-bd6d-fc0422633260)
![image](https://github.com/user-attachments/assets/e253ffbd-17e7-4901-838d-4d70faed0069)
![image](https://github.com/user-attachments/assets/9425653c-5820-4af4-bab3-a8f659a02e46)
![image](https://github.com/user-attachments/assets/264b0f56-c997-42ea-8e71-6d4935ee87f9)

### vii) HSV to RGB and BGR

import cv2
img = cv2.imread('1.JPEG')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()

## Output:
![image](https://github.com/user-attachments/assets/c1f0559a-4ced-4ab3-a31f-def3c6d84a48)
![image](https://github.com/user-attachments/assets/64bb3b76-22fe-452f-991b-cf416500baa0)
![image](https://github.com/user-attachments/assets/ae5fe8b5-a403-4d3b-8cc0-559b34bec342)

### viii) RGB and BGR to YCrCb

import cv2
img = cv2.imread('1.JPEG')
img = cv2.resize(img,(300,300))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()

## Output:
![image](https://github.com/user-attachments/assets/c43554cf-4193-4d19-85ba-b98a67c84a2a)
![image](https://github.com/user-attachments/assets/8146304d-e7a1-496b-be08-71db52bcb60a)
![image](https://github.com/user-attachments/assets/16f797d5-14d1-4c87-b446-37386e0cdc64)

### ix) Split and merge RGB Image

import cv2
img = cv2.imread('1.JPEG')
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()

## Output:
![image](https://github.com/user-attachments/assets/607d1197-7155-461a-8ec0-5c8f08cf5aa7)
![image](https://github.com/user-attachments/assets/f51868df-1204-4077-938c-c4e7a8c7e150)
![image](https://github.com/user-attachments/assets/df7e6fe4-7711-4d26-9a73-4b180aeb4de3)
![image](https://github.com/user-attachments/assets/05ef8215-2b66-44c7-bba0-025f4ca5860c)

### x) Split and merge HSV Image

import cv2
img = cv2.imread('1.JPEG')
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()

## Output:
![image](https://github.com/user-attachments/assets/c15e5e52-f733-48d1-a7c8-03ae3d4879d3)
![image](https://github.com/user-attachments/assets/1d925838-675a-4ff0-abad-cf90c966d8ed)
![image](https://github.com/user-attachments/assets/a5a7925f-4366-4660-8b46-acb2787594fc)
![image](https://github.com/user-attachments/assets/c675d396-379d-459e-b4f0-fce63b31be1f)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
