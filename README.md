Webcam Video Capture & Saving for Python
This Python script captures video from the default webcam, and saves and displays the video stream in real-time. The captured video stream then gets saved as an AVI file. Note that the video capture will continue until the user manually stops it.
Dependencies
You must have the following libraries for Python:
OpenCV: This open-source computer vision and machine learning library is necessary for video capture and manipulation. You can install it using pip with .pip install opencv-python
NumPy: This library is used for scientific computing in Python. It can be installed with .pip install numpy
Usage
To use, initialize the script in a Python environment. The script will open a new window showing the video stream from the webcam. The video stream will be saved to . To stop the video capture, press the key on your keyboard.output.aviq
Understanding the Code
This script uses OpenCV's and objects for accessing the webcam and writing the video file, respectively.VideoCaptureVideoWriter
It sets up video capture through , where often refers to the default webcam. If you have multiple video inputs, you may need to change this value.cv2.VideoCapture(0)0
The object takes four arguments:cv2.VideoWriter
'output.avi': The output file name.
FourCC code: This code helps determine the codec used in the video compression. The code refers to one of the more popular codecs.*'XVID'
Frames per second: Here, we specify FPS for our video.20.0
Frame size: The tuple refers to the dimensions of the output video.(640, 480)
The script operates in a loop, capturing each frame and writing it into .whileoutput.avi
The display is handled through , and the script listens for the key to break the loop and stop the video capture.cv2.imshow()q
Upon breaking the loop, the video capture and writer are released with , and any created windows are destroyed with .release()cv2.destroyAllWindows()
