# LGMVIP-DataScience internship
# Task 4- Image to Pencil Sketch with Python

cv2 library: OpenCV is a cross-platform library using which we can develop real-time computer vision applications. It mainly focuses on image processing, video capture and analysis including features like face detection and object detection

In this task, 

first we need to import the cv2 library then find an image that you want to convert to a pencil sketch with Python, read that image by 
image= cv2.imread, 

then we need to read the image in RBG format by 
img_rgb= cv2.cvtColor(image, cv2.COLOR_BGR2RGB) 

and then convert it to a grayscale image 
gray_image= cv2.cvtColor(image, cv2.COLOR_BGR2GRAY), 

invert the grayscale image also called negative image by 
inverted_image= 255 - gray_image 

then convert it into blurry image(Gaussian function)
blurred = cv2.GaussianBlur(inverted_image, (21, 21), 0), 

by dividing the grayscale image by the inverted blurry image 
inverted_blurred = 255 - blurred

then finally create the pencil sketch by mixing the grayscale image with the inverted blurry image
pencil_sketch = cv2.divide(gray_image, inverted_blurred, scale=256.0)

And to Display image at anytime
cv2.imshow("Diksha Sketch", pencil_sketch)
cv2.waitKey(0)
