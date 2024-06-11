# Webcam Video Capture & Saving for Python

This Python script captures video from the default webcam, and saves and displays the video stream in real-time. The captured video stream then gets saved as an AVI file. Note that the video capture will continue until the user manually stops it.

## Dependencies

You must have the following libraries for Python:

- OpenCV: This open-source computer vision and machine learning library is necessary for video capture and manipulation. You can install it using pip with .pip install opencv-python

- NumPy: This library is used for scientific computing in Python. It can be installed with .pip install numpy

## Usage
To use, initialize the script in a Python environment. The script will open a new window showing the video stream from the webcam. The video stream will be saved to . To stop the video capture, press the key on your keyboard.output.aviq

## Understanding the Code.

The script uses OpenCV libraries to interact with the hardware (webcam) and capture video:

- It initializes a connection to the webcam with the `cv2.VideoCapture(0)` function. The parameter '0' in this function refers to the default webcam. If you have multiple webcams, you can switch between them by changing the parameter (1, 2, etc.).

- We then specify the video codec using the `cv2.VideoWriter_fourcc('XVID')` function and define a VideoWriter object. We pass the name of the output video file ('output.avi'), the specified codec, the number of frames per second (20.0), and the frame size (640x480) to this object.

- In the main loop of the program, we continuously read and display each frame. The `cap.read()` function reads the next frame from the video (webcam feed in this case). The frame is then written to the output file using `out.write(frame)`, and also displayed in an OpenCV window with the `cv2.imshow('frame', frame)` function.

- The loop continues until the user presses 'q' on their keyboard, the `cv2.waitKey(1) & 0xFF == ord('q')` statement detects this. Once 'q' is detected the capture is stopped, the video file is saved, and all windows are destroyed.

Bear in mind that in this script, the frames are saved as they are captured, without any flipping. However, if you need to flip each frame vertically for some reason, you can uncomment and use the command `frame = cv2.flip(frame,0)`.
