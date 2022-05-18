# Video Player

I created a program that can play videos in the terminal using ASCII characers.

The progam is made in python since it has many libraries that helped me in doing some things. The downside, is, that python is really slow, and if written in another language the progarm could've been faster.

## So how does the program work?

*Firstly,* we need to get the video. The user has the abilitty to provide a video from their computer, or if they want, they can get it from YouTube.
If they want to get the video, we will download it using `youtubedl` library, and then run the program as we would run it normally (with a video from our computer), but this time providing the file path to the newly downloaded video. Except for 1 difference, if we download a video from YouTube, we can also get the subtitles and write them on the terminal (since we cannot listen to audio).

*Later, after downloading the video,* we would use `OpenCV`, one of the numerous python libraries, we would use it to separate all the frames in a video into several images. Then using `Pillow (PIL)` library we will resize those new images into the terminal size (so if the original video is 1920x1080 pixels and the terminal is 150x80 characrers, then each frame would be resized to the terminal size). We would also convert the image to gray-scale, by finding the average of the RGB values in a pixel.

*Now that, we got all the frames and resized them,* it's time to actually draw them on the screen.

We would iterate over all images, and in each image, over every pixel and draw an ASCII character depending on it's gray-scale value on the place needed on the screen.

After drawing a frame we draw the already download subtitles at the bottom of the screen depending on the time in the video.

Since, we are using python, our program is slow, so frames are also drawn slowly. The smaller the terminal scale the faster frames would render, the bigger the slower.

Here is the [source code](https://github.com/thealexdev23/terminal-video-player)
