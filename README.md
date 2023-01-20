# FACE RECOGNITION AND COMPARISON SYSTEM USING OPENCV

In this project with OpenCV and Python, through a database we compare the person's photo and we know how to identify it precisely. Along with that we will be building a face recognition system which can be used for safety purposes.

## INTRODUCTION

A facial recognition system is a technology capable of matching a human face from a digital image or a video frame against a database of faces. Such a system is typically employed to authenticate users through ID verification services, and works by pinpointing and measuring facial features from a given image.

<p align="center">
  <img src="https://user-images.githubusercontent.com/114398468/213382172-ca797f04-183f-472d-883a-cfd51d91ee37.png" />
</p>


## PACKAGES USED

 - OpenCV
 - face_recognition
 

## Steps to Replicate This Project

### 1. Clone the github repository by typing the following commands

```
# Clone
git clone (https://github.com/CHRISTInfotech/AI-IoT-Basic-Projects.git)
cd FACE RECOGNITION SYSTEM USING OPENCV
```

### 2. INSTALL THE NECESSARY PACKAGES 
  - For installing the openCV use the following command
    ```
    pip install opencv-python
    ```
  - For installing the face recognition package use
    ```
    pip install face_recognition
    ```

### 3. FOR COMAPRING THE TWO IMAGES:
  - **CALLING THE LIBRARIES**:
    ```
    import cv2
    import face_recognition
    ```
  - **Face encoding first image**
      - With the usual OpenCV procedure, we extract the image, in this case ```Messi1.webp``` and convert it into RGB color format. Then we do the “face encoding” with
      - the function of face recognition library
        ```
        img = cv2.imread("Messi1.webp")
        rgb_img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
        img_encoding = face_recognition.face_encodings(rgb_img)[0]
        ```
        
   - **Face encoding second image**
      - Same procedure for the second image, we only change the name of the variables and obviously the path of the second image, in this case: images/Messi.webp.
          ```
          img2 = cv2.imread("images/Messi.webp")
          rgb_img2 = cv2.cvtColor(img2, cv2.COLOR_BGR2RGB)
          img_encoding2 = face_recognition.face_encodings(rgb_img2)[0]
          ```
   - **Comparison of images**
       - With a single line, we make a simple face comparison and print the result. If the images are the same it will print True otherwise False.
          ```
          result = face_recognition.compare_faces([img_encoding], img_encoding2)
          print("Result: ", result)
          ```
### 4. FOR FACIAL RECOGNITION :
  - Open the ```main_video.py``` in the files. It imports files from the ```simple_facerec.py```
  - Choose the camera according to the choice ie __0: webcam__, __1: External cam__

## OUTPUT:
- **__FACIAL RECOGNITION OUTPUT__**

<p align="center">
  <img src="https://user-images.githubusercontent.com/114398468/213403214-77eb6e9c-ce63-4317-b5a4-98582ec9daaa.png" />
</p>

-  **The link for the video to the real time working of this project is given below:**


https://user-images.githubusercontent.com/114398468/213629808-0a93a5e6-aeff-440a-b2ab-00a10a7bdb2c.mp4

[__https://drive.google.com/file/d/1smZeWuHjSHhVnOGKwEcIdXeKApollyQS/view?usp=drivesdk__]
   
## REFERENCE:
 - https://www.kaspersky.com/resource-center/definitions/what-is-facial-recognition
 - https://www.analyticsvidhya.com/blog/2021/06/learn-how-to-implement-face-recognition-using-opencv-with-python/
