# virtual-mouse
Imports necessary libraries: cv2 for computer vision, mediapipe for hand detection, and pyautogui for controlling the mouse cursor.
Sets up the webcam feed using cv2.VideoCapture(0).
Initializes the hand detector and drawing utilities from Mediapipe.
Retrieves the screen size using pyautogui.size() to map hand gestures to screen coordinates.
Enters a loop to continuously read frames from the webcam.
Processes each frame to detect hands using the hand_detector.process() method.
If hands are detected, it iterates over each detected hand, draws landmarks on the frame, and retrieves specific landmarks (e.g., index finger and thumb) to control the virtual mouse.
Maps the coordinates of the detected landmarks to the screen coordinates using the screen size obtained earlier.
Moves the mouse cursor using pyautogui.moveTo() based on the position of the index finger.
Checks the distance between the index finger and thumb to determine if a click action should be performed.
If the distance is below a certain threshold, it simulates a mouse click using pyautogui.click().
The cv2.imshow() function displays the processed frame with the virtual mouse cursor, and cv2.waitKey(1) waits for a key press (with a delay of 1 millisecond) before processing the next frame.
