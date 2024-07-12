# VEHICLE DETECTION AND COUNTER SYSTEM

This Python-based project implements a vehicle detection and counter system using computer vision techniques. The system is designed to detect vehicles in a given video stream or set of images, count them as they enter or exit a specified region (like a parking lot or a road segment), and display or log the count results.

![Screenshot (63)](https://github.com/user-attachments/assets/8faf962d-7002-4fca-b929-a30e02b8d785)

## Overview

This Python script is designed to detect and count vehicles in a given video file using computer vision techniques provided by OpenCV. The script processes each frame of the video to identify and count the vehicles as they cross a predefined line on the screen.

## How does it work?

## STEP 1 Import Libraries:

The script imports necessary libraries: OpenCV (cv2) for image and video processing, and NumPy (np) for numerical operations.

## STEP 2 Video Capture:

cap = cv2.VideoCapture("video.mp4") initializes video capture from a file named "video.mp4". This can be replaced with 0 to use a web camera.

## STEP 3 Detection Parameters:

min_width_react and min_height_react define the minimum width and height of the detected rectangles (bounding boxes) to filter out small detections that are likely not vehicles.
count_line_positon specifies the position of the line on the screen that vehicles must cross to be counted.
## STEP 4 Background Subtraction:

The script uses a background subtraction algorithm, specifically cv2.bgsegm.createBackgroundSubtractorMOG(), to separate moving vehicles from the background.
## STEP 5 Helper Function:

center_handle(x,y,w,h) computes the center point of a bounding box, which helps in tracking vehicles.

## STEP 6 Main Processing Loop:

The script reads frames from the video in a loop using cap.read().
Each frame is converted to grayscale (cv2.cvtColor) and blurred (cv2.GaussianBlur) to reduce noise.
Background subtraction is applied to the blurred frame to get a foreground mask (algo.apply).
The mask is further processed with dilation and morphological transformations to improve the detection (cv2.dilate, cv2.morphologyEx).

## STEP 7 Contour Detection:

The script finds contours in the processed mask (cv2.findContours), which represent detected vehicles.
For each contour, it calculates a bounding box (cv2.boundingRect) and filters out small boxes.

## STEP 8 Vehicle Detection and Counting:

Bounding boxes are drawn around detected vehicles (cv2.rectangle).
The center of each bounding box is calculated and tracked.
If a vehicle's center crosses the counting line (count_line_positon) within a defined offset, it is counted, and the count is displayed on the frame (cv2.putText).

## STEP 9 Display and Termination:

The processed frames (with detections and counts) are displayed in windows (cv2.imshow).
The loop breaks and the video capture is released when the 'Enter' key is pressed (cv2.waitKey).


## Demo  
https://github.com/user-attachments/assets/63c6c332-dd24-4045-9799-d87376afe865

## Inspiration
Vehicle detection and counting systems can revolutionize traffic management by optimizing flow and reducing congestion in smart cities. They enhance public safety by monitoring sensitive areas and detecting incidents in real-time. These systems contribute to environmental sustainability by analyzing emissions and noise pollution data. In commercial applications, they improve parking management and provide valuable retail analytics. For research, they offer opportunities to advance computer vision and machine learning. The automotive industry benefits through autonomous driving and fleet management optimization. Future innovations include IoT integration, AI-powered analytics, and 5G connectivity, promising even greater advancements



## Screenshot
![Screenshot (68)](https://github.com/user-attachments/assets/5fc4a1e9-9795-4690-b7b4-2d16abf6ad67)



## Dependencies
      
The project requires the following libraries and Tools:

- Python
- OpenCV (cv2)
- NumPy (np)
- Video File

  
## Installation

1. Clone the repo:
   ```sh
   git clone https://github.com/Keerthana1417/Vehicle-detection   
2. Navigate to the project directory
   
   cd Vehicle-detection 
## Usage

### Run the main.py script:
   
    vehicle.py


## Contributing

Contributions to this repository are welcome! If you find any issues, have suggestions, or want to improve the code, feel free to submit a pull request.

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Contact

Keerthana - [keerthanasamala1411@gmail.com](mailto:your.email@example.com)

Project Link: [https://github.com/Keerthana1417/Vehicle-detection ]  

### Happy detecting and learning!
