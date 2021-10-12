# Image-Cartoonifier
- This mini project is cartoonifying an image with OpenCV in Python. 
Steps to build-
1. Import the necessary libraries
   - cv2(for image processing OpenCV) 
   - easygui(to open a file box as it allows us to select any file from our system)
   - numpy
   - imageio(to read the file which is chosen by file box)
   - matplotlib(used for visualization and plotting)
2. Create a File Box to choose the file
   - fileopenbox() is the method in easyGUI module which returns the path of the chosen file as a string. This code opens the file box everytime you run the code to choose the file from the device.
3. To store the image
   - imread is a method in cv2 which aloows us to store images in the form of numbers and perform operations on it. The image is read as a numpy array, in which cell values depict R, G, and B values of a pixel.
4. Transform the color image to grayscale image
   - cvtColor is a method in cv2 which transforms an image into the colour-space mentioned as ‘flag’. We use the BGR2GRAY flag. This returns the image in grayscale.
   - After each transformation, we resize the resultant image using the resize() method in cv2 and display it using imshow() method.
5. Smoothening the grayscale image
   -  we simply apply a blur effect to smoothen an image. We use the medianBlur() function for this purpose. The center pixel is assigned a mean value of all the pixels therefore creating a blur effect.
6. Retrieving the edges of the image
   - The main features of a cartoon image is smoothened colours and highlighted edges. We have done the smoothening. For highlighting the edges, we will retrieve the edges and highlight them using adaptive threshold technique.
   - The threshold value is the mean of the neighborhood pixel values area minus C.
   - C is a constant that is subtracted from the mean or weighted sum of the neighborhood pixels
7. Prepare a Mask Image
   - bilateralFilter is used to remove the noise
   - sigmaColor and sigmaSpace make an image look vicious and like water paint, removing the roughness in colors(also known as sigma effect).
8. Cartoonify our image
   - the two main features of a cartoon image is combined together using masking.
   - A mask is a binary image consisting of zero- and non-zero values. If a mask is applied to another binary or to a grayscale image of the same size, all pixels which are zero in the mask are set to zero in the output image. All others remain unchanged.
   - Masking is an image processing method in which we define a small 'image piece' and use it to modify a larger image.
   - we mask our edged image on our smoothened image to give the cartoon image.
