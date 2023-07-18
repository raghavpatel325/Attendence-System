# Attendence-System

steps to run this project:-

1.Add the images in student folder

2.open main file

3.attendence will automatically updated in csv file with person name and time

--> suitable for low to medium sized organiztions

dependencies required:

face_recognition: This is a Python library for face recognition and facial feature detection. It can be installed using pip install face_recognition.

cv2: This is the OpenCV library, which is used for computer vision tasks, including image and video processing. It can be installed using pip install opencv-python.

numpy: This is a fundamental package for scientific computing with Python. It provides support for large, multi-dimensional arrays and matrices. It can be installed using pip install numpy.

csv: This is a built-in module in Python for reading and writing CSV files. It does not require installation as it is part of the Python standard library.

os: This is a built-in module in Python that provides a way to interact with the operating system. It does not require installation as it is part of the Python standard library.

datetime: This is a built-in module in Python that provides classes for working with dates and times. It does not require installation as it is part of the Python standard library.

Make sure to install the required dependencies using pip install before running the code.

.................................................................................................................................................

This project is an attendance system that uses face recognition to track the presence of individuals in a video stream :

Importing Libraries: The project starts by importing the necessary libraries, such as face_recognition, cv2 (OpenCV), numpy, csv, os, and datetime. These libraries provide functions and tools for face recognition, video capturing, data manipulation, and time-related operations.

Loading Face Images and Encodings: Several face images of known individuals are loaded using the face_recognition.load_image_file() function. These images are then encoded using the face_recognition.face_encodings() function, which generates a numerical representation (encoding) of each face.

Creating Lists of Known Faces: The encoded face data is stored in a list called known_face_encoding, and the corresponding names are stored in the known_faces_names list. This list serves as a reference for identifying the individuals.

Initializing Variables and Files: Various variables and files are initialized. For example, the video capture device is opened (cv2.VideoCapture()), and a CSV file is created to store attendance data.

Face Recognition Loop: The project enters an infinite loop to continuously capture frames from the video stream. Each frame is resized and converted to RGB format for face recognition.

Face Recognition and Attendance Tracking: The face_recognition library is used to locate faces in the frame (face_recognition.face_locations()) and encode them (face_recognition.face_encodings()). The encoded faces are compared (face_recognition.compare_faces()) with the known face encodings.

Displaying and Updating Attendance: If a match is found, the corresponding name is assigned to the face. The recognized name is displayed on the frame using OpenCV's cv2.putText() function. If the recognized name is one of the students in the students list, it means the student is present, so their name is removed from the list, and the current time is recorded in the CSV file.

Exiting the Program: The processed frame with the displayed names is shown on the screen using cv2.imshow(). Pressing 'q' on the keyboard quits the program (cv2.waitKey(1) & 0xFF == ord('q')).

Cleanup: After exiting the loop, the video capture is released (video_capture.release()) and the OpenCV windows are closed (cv2.destroyAllWindows()). The CSV file is closed (f.close()).

Overall, this project continuously captures video frames, recognizes faces using preloaded images, and updates attendance by comparing recognized faces with known faces.
