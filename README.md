# WORKSHOP 3 : Canny Edge Detection

## Aim
To implement the Canny Edge Detection algorithm on a sample image using Python and OpenCV, and analyze the effect of different threshold parameters on the detected edges.

## Algorithm
1. Read the input image.
2. Convert the image from BGR to grayscale.
3. Apply Gaussian Blur to reduce noise.
4. Apply the Canny Edge Detection algorithm.
5. Use different lower and upper threshold values.
6. Display the detected edges.
7. Compare the results for different threshold settings.
8. Analyze the effect of the parameter changes.

## Program
```python
import cv2
import matplotlib.pyplot as plt

# Read the sample image
image = cv2.imread("golden-bird.jpg")

# Display results
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis("off")

```
```python
# Convert to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display results
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 2)
plt.imshow(gray, cmap="gray")
plt.title("Grayscale Image")
plt.axis("off")
plt.show()
```
```python
# Apply Gaussian Blur
blur = cv2.GaussianBlur(gray, (5, 5), 0)

# Apply Canny Edge Detection
edges = cv2.Canny(blur, 50, 100)

# Display results
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 3)
plt.imshow(edges, cmap="gray")
plt.title("Canny Edges")
plt.axis("off")

plt.show()
```
```python
# Apply Canny Edge Detection using different parameters

edges1 = cv2.Canny(blur, 50, 150)
edges2 = cv2.Canny(blur, 100, 200)
edges3 = cv2.Canny(blur, 150, 250)

# Display all results together
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(edges1, cmap="gray")
plt.title("Canny: 50, 150")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(edges2, cmap="gray")
plt.title("Canny: 100, 200")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(edges3, cmap="gray")
plt.title("Canny: 150, 250")
plt.axis("off")

plt.show()
```

## Output

## Result
The Canny Edge Detection algorithm was successfully implemented using Python and OpenCV. The main edges of the bird, including its wings, body, and feathers, were detected. Different threshold values produced different levels of edge details.
