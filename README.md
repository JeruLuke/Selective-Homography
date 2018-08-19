# Interactive-Homography
Sometimes theremight be a need to engrave one image into another. Homography can help you achieve that. This easy-to-understand repo has an implementation using OpenCV to choose where you want to engrave an image at a location of your choice.

To know more about Homography visit the [blog post by Satya Mallick](https://www.learnopencv.com/homography-examples-using-opencv-python-c/). It is written in a way easy to understand along with code examples in Python and C++. Towards the end of the post he mentions the steps to make a virtual billboard. This is what I am about to demonstrate here. 

I have an image of a street in New York (the image in the blog) and would like to place an image having the cast of Spartacus (TV series) on one of their billboards.

Here are the images used:

1. The street of New York city:

![alt text](https://github.com/JeruLuke/Interactive-Homography/blob/master/billboard.jpg)

2. The cast of the TV series Spartacus:

![alt text](https://github.com/JeruLuke/Interactive-Homography/blob/master/Spartacus.jpg)

## Software and Installation

Any version of Python with OpenCV version 3.0.0 (at the least).

## Project Structure

```
Main Folder
  --> homography_mouseclick.py
  --> homography_mouseclick_argument.py
  --> billboard.jpg (base image)
  --> Spartacus.jpg (inner image)
  --> results
      --> mask.jpg
      --> Spartacus_billboard.jpg
      --> warped.jpg
```

## How to run it?

Open the terminal, navigate to the location of the repository and execute the following:

`python homography_mouseclick_argument.py -b billboard.jpg -s Spartacus.jpg`

Notice the two arguments:

1. `-b` takes in the base image (the image where the other image is to be placed). Here it is `billboard.jpg`.
2. `-s` takes in the inner image to be placed (otherwise called homographed image). Here it is `Sapartacus.jpg`.

Upon execution both the input images would show up. Choose **four** points on the base image where you want the other image to be placed. Selection of points must be in anti-clockwise direction starting from top-left, in other words: top-left -> top-right -> bottom-right -> bottom_left.

After choosing the four points correctly, the program displays 3 windows:
1. A window with the homographed image warped in with dimensions of the base image. (`warped.jpg`)
2. Another window containing the mask which needs to be added with the previous image. (`mask.jpg`)
3. The expected result.

## Result

The following are the warped and mask images repectively:

![alt text](https://github.com/JeruLuke/Interactive-Homography/blob/master/results/warped.jpg)

![alt text](https://github.com/JeruLuke/Interactive-Homography/blob/master/results/mask.jpg)

The following is the intended result. Notice the billboard on the left with the cast of Spartacus:

![alt text](https://github.com/JeruLuke/Interactive-Homography/blob/master/Spartacus_billboard.jpg)

Some other results:

Notice the billboard on the right:

![alt text](https://github.com/JeruLuke/Interactive-Homography/blob/master/Spartacus_billboard_2.jpg)

Notice the cast on the building to the left:

![alt text](https://github.com/JeruLuke/Interactive-Homography/blob/master/Spartacus_billboard_3.jpg)
