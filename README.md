## AIM
To write a python program using OpenCV to do the following image manipulations.
## Software Required:
Anaconda - Python 3.7
## Algorithm:
```
1. Read and Display an Image:

Load an image from your local directory and display it.

2. Draw Shapes and Add Text:

Draw a line from the top-left to the bottom-right of the image.

Draw a circle at the center of the image.

o Draw a rectangle around a specific region of interest in the image.

Add the text "OpenCV Drawing" at the top-left corner of the image.

3. Image Color Conversion:

Convert the image from RGB to HSV and display it.

Convert the image from RGB to GRAY and display it.

O Convert the image from RGB to YCrCb and display it.

Convert the HSV image back to RGB and display it.

4. Access and Manipulate Image Pixels:

Access and print the value of the pixel at coordinates (100, 100). Modify the color of the pixel at (200, 200) to white.

5. Image Resizing:

Resize the original image to half its size and display it.

6. Image Cropping:

Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

7. Image Flipping:

Flip the original image horizontally and display it.

Flip the original image vertically and display it.

8. Write and Save the Modified Image:

Save the final modified image to your local directory.
```

## Program:
#### Developed By: Guttha Keerthana
#### Register Number: 212223240045


### 1) Read and display the image
```
import cv2
image=cv2.imread('ex1.jpg',1)
cv2.imshow('Image Window', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output:
![image](https://github.com/user-attachments/assets/f35b1eb4-c124-4198-98f9-fe44f8a025f4)

### 2.) Draw Shapes and Add Text:
#### i)Draw a line from the top-left to the bottom-right of the image.
```
import cv2
img = cv2.imread("ex1.JPG")
res = cv2.line(img, (0, 0), (599, 799), (200, 100, 205), 10)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output:
![image](https://github.com/user-attachments/assets/66f70e56-4e3b-4c2b-adaa-3215404026b5)

### ii)Draw a circle at the center of the image.

```
import cv2

# Load the image
img = cv2.imread("ex1.JPG")

# Get the dimensions of the image
height, width, _ = img.shape

# Calculate the center of the image
center_coordinates = (width // 2, height // 2)

# Draw a circle at the center of the image
res = cv2.circle(img, center_coordinates, 150, (255, 0, 0), 10)

# Display the image with the circle
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
![image](https://github.com/user-attachments/assets/b4115b72-89bd-4d52-bb92-4a5b1edd1c03)

### iii)Draw a rectangle around a specific region of interest in the image.
```
import cv2

img = cv2.imread("ex1.JPG")
start=(0,0)
stop=(409,529)
color=(100,255,100)
thickness=10
res_img=cv2.rectangle(img,start,stop,color,thickness)
# Display the HSV image
cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/479f5984-80a4-4c86-8f2d-aadcf066ad72)


### iv)Add the text "OpenCV Drawing" at the top-left corner of the image.
```
import cv2

# Load the image
img = cv2.imread("ex1.JPG")

# Define the text to be added and its position
text = "OPENCV DRAWING"
position = (50, 50)  # Positioning the text at the top-left corner

# Set the font, scale, color, and thickness of the text
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
color = (255, 255, 255)  # White color
thickness = 2

# Add the text to the image
res = cv2.putText(img, text, position, font, font_scale, color, thickness, cv2.LINE_AA)

# Display the image with the text
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```

### Output:
![image](https://github.com/user-attachments/assets/8fd79330-6791-4b25-9823-634dcd8da0d5)

### 3.)Image Color Conversion:

#### i)Convert the image from RGB to HSV and display it.

```
import cv2
img = cv2.imread('ex1.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/5b1cd35e-fccb-4c1c-9a00-9b4b159ef58d)
![image](https://github.com/user-attachments/assets/abee7e2d-b769-496b-9fd4-fd1f19fc0808)

#### ii.)Convert the image from RGB to GRAY and display it.
```
import cv2
img = cv2.imread('ex1.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/7f1c1965-59f0-4b56-9b6b-e10c6923c04f)
![image](https://github.com/user-attachments/assets/c017f9ff-140c-4d94-9d30-fd0925ddc13e)

#### iii.)Convert the image from RGB to YCrCb and display it.
```
import cv2
img = cv2.imread('ex1.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/901eb0aa-232d-473d-a761-63c092e1ad68)
![image](https://github.com/user-attachments/assets/88fa6748-afd8-42f2-9352-960e8d6cf83a)

#### iv.)Convert the HSV image back to RGB and display it.
```
import cv2
img = cv2.imread('ex1.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/45f70183-41b8-4710-ba5a-16d11490e4db)
![image](https://github.com/user-attachments/assets/390a0392-107c-4a10-9e35-197b18cef697)

### 4. Access and Manipulate Image Pixels:
```
import cv2

# Load and resize the image
img = cv2.imread('ex1.jpg', 1)
img = cv2.resize(img, (300, 200))

# Show the original image
cv2.imshow('Original Image', img)

# 1. Access and print the value of the pixel at coordinates (100, 100)
pixel_value = img[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# 2. Modify the color of the pixel at (199, 199) to white
img[199, 199] = [255, 255, 255]  # Setting the pixel value to white (BGR)

# Display the modified image
cv2.imshow('Modified Image', img)

# Wait for a key press and close the windows
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
![image](https://github.com/user-attachments/assets/c47d9c54-5eda-4a45-846b-77cc05f5b01e)
![image](https://github.com/user-attachments/assets/ac6bb990-e287-4dd3-aeea-379d88f66eb2)
![image](https://github.com/user-attachments/assets/40b1f0d3-0f2b-49de-ae60-0f5cef3cca3f)

### 5. Image Resizing:
```
width=600
height=800
half_width=300
half_height=400
resized_img = cv2.resize(image, (300, 400))
cv2.imshow('Original',image)
cv2.imshow('resized',resized_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
![image](https://github.com/user-attachments/assets/11339545-9eda-4828-902e-cc7d642b5a40)
![image](https://github.com/user-attachments/assets/bb885a5f-468a-42ea-bac4-f0f06f7a5209)

### 6.Image Cropping:

```
import cv2

# Load the image
image1=cv2.imread('sun.jpg',1)

# Define the starting point and size of the ROI
x, y = 50, 50
width, height = 100, 100

# Crop the ROI
roi = image1[y:y + height, x:x + width]

# Display the cropped ROI
cv2.imshow('Cropped Image', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/fd9b8da4-a455-45fb-b473-857c6382fb0e)

### 7.Image Flipping:
#### i.)Flip the original image horizontally and display it.
```
import cv2
img = cv2.imread("ex1.JPG")
img = cv2.resize(img,(300,200))
res=cv2.rotate(img,cv2.ROTATE_180)
cv2.imshow('Original',img)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/55c8afb9-7008-4db5-b748-74b9c449339d)
![image](https://github.com/user-attachments/assets/f9d4ef0d-ca2a-4f28-8b6c-d0795383fdd5)

#### ii.)Flip the original image vertically and display it.
```
import cv2

img = cv2.imread("ex1.JPG")
img = cv2.resize(img,(300,200))
res=cv2.rotate(img,cv2.ROTATE_90_CLOCKWISE)
# Display the HSV image
cv2.imshow('Original',img)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/991cf8c4-ffd0-4e77-81a3-0da44aee851a)
![image](https://github.com/user-attachments/assets/9cc8b457-66d9-4a0e-b4b0-38c1f1574323)

### 8. Write and Save the Modified Image:
```
import cv2
img = cv2.imread("ex1.JPG")
img = cv2.resize(img,(300,200))
cv2.imwrite('sunny1.jpg',img)
```
### Output:
![image](https://github.com/user-attachments/assets/50a98782-239a-490f-a223-26e23ccb0804)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
