CNN based Sudoku-Solver

Sudoku is one of the most popular puzzle of all time.The goal of Sudoku is to fill 9x9 grid such that each row,each column and 3x3 grid contains all of the digits between 1 to 9. In this project we aim to create a real time Sudoku solver which recognise the elements of Sudoku puzzle and providing a digital solution using Computer vision.

Steps

Grab the Sudoko Grid from the Webcam Image
Extract and Detect the Digits
Solve the puzzle and Print the Solution
1. Grab the Sudoko Grid from the Webcam Image
Extracting the Contour with biggest area
Convert image to Gray scale (cv2.cvtColor)
Blur the image using Gaussian Blur (cv2.GaussianBlur)
Apply adaptive thresholding (cv2.adaptiveThreshold)
Extract the contour with biggest area (cv2.contourArea)

<img width="720" height="720" alt="image" src="https://github.com/user-attachments/assets/9b2cf13d-c04b-45ee-9082-969a13f599a7" />

2. Extract and Detect the Digits
Process the Extracted Grid
Use cv2.morphologyEx and Invert the image
 
<img width="533" height="533" alt="image" src="https://github.com/user-attachments/assets/0b46238e-5fed-43de-9f1e-6dec4b2bc96c" /><img width="537" height="533" alt="invert image" src="https://github.com/user-attachments/assets/fa218d89-b69c-43a6-915f-7920fc0f1245" />


Get Individual Cells of the grid and Predict the Digit
Model used for prediction has been trained on subset of Chars74K Dataset which contains digits only (0-9). Weights upgradation of model can be viewed in OCR.h5 file.

While predicting the digits, blank cells would be predicted as 0. Blank cells can be identified by calculating sum of all the pixels (sum would be large)

3. Solve the puzzle and Print the Solution
Solution and Final Result
To solve Sudoku, backtracking has been used. Sudoku Backtracking is a recursive algorithm which goes through each cells and sequentially assigns numbers from 1 to 9 if the cell is empty.

<img width="540" height="537" alt="image" src="https://github.com/user-attachments/assets/8ed79745-f797-47a2-a8dc-e53b17e548c8" />


To display the result use cv2.putText.

