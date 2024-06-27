# Simple-Image-Recognition-
Build a simple image recognition system using OpenCV

import cv2
import numpy as np

# Load the image
img = cv2.imread('image.jpg')

# Convert to grayscale
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# Load the classifier
cascade = cv2.CascadeClassifier('classifier.xml')

# Detect objects
objects = cascade.detectMultiScale(gray, scaleFactor=1.1, minNeighbors=5)

# Draw rectangles around detected objects
for (x, y, w, h) in objects:
    cv2.rectangle(img, (x, y), (x+w, y+h), (0, 255, 0), 2)

# Display the output
cv2.imshow('Image', img)
cv2.waitKey(0)
cv2.destroyAllWindows()
