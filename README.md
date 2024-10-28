<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Convolution and Edge Detection with Sobel Operators</title>
</head>
<body>

<h1>Image Convolution and Edge Detection with Sobel Operators</h1>

<p>
    <img src="https://img.shields.io/badge/Python-3.x-blue.svg" alt="Python Badge">
    <img src="https://img.shields.io/badge/OpenCV-4.x-green.svg" alt="OpenCV Badge">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License Badge">
</p>

<p>This project demonstrates image processing using Sobel operators for edge detection, an essential tool in image analysis for tasks such as object recognition, segmentation, and contour detection.</p>

<h2>Table of Contents</h2>
<ul>
    <li><a href="#overview">Overview</a></li>
    <li><a href="#requirements">Requirements</a></li>
    <li><a href="#project-structure">Project Structure</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#example-output">Example Output</a></li>
    <li><a href="#explanation-of-sobel-operators">Explanation of Sobel Operators</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
</ul>

<h2 id="overview">Overview</h2>
<p>
    The notebook focuses on:
</p>
<ol>
    <li><strong>Loading an Image</strong>: Reading an image in grayscale format for processing.</li>
    <li><strong>Applying Sobel Filters</strong>: Using Sobel operators in horizontal and vertical directions to detect edges.</li>
    <li><strong>Combining Gradients</strong>: Calculating the combined gradient magnitude to obtain the final edge-detected image.</li>
</ol>

<h2 id="requirements">Requirements</h2>
<p>To run the code, ensure the following Python packages are installed:</p>
<pre><code>pip install numpy opencv-python</code></pre>

<h2 id="project-structure">Project Structure</h2>
<ul>
    <li><strong>Introduction</strong>: Explanation of Sobel filtering and edge detection concepts.</li>
    <li><strong>Image Loading</strong>: Code to load and display the target image.</li>
    <li><strong>Sobel Filter Application</strong>: Applying Sobel filters in x and y directions.</li>
    <li><strong>Gradient Combination</strong>: Combining gradients to generate the final edge-detected image.</li>
</ul>

<h2 id="usage">Usage</h2>
<ol>
    <li><strong>Load an Image</strong>:</li>
    <pre><code>import cv2
image = cv2.imread</code></pre>

    <li><strong>Apply the Sobel Filter</strong>:</li>
    <pre><code>sobel_x = cv2.Sobel(image, cv2.CV_64F, 1, 0, ksize=3)
sobel_y = cv2.Sobel(image, cv2.CV_64F, 0, 1, ksize=3)</code></pre>

    <li><strong>Combine the Results</strong>:</li>
    <pre><code>sobel_combined = cv2.magnitude(sobel_x, sobel_y)</code></pre>

    <li><strong>Display the Results</strong> (Optional):</li>
    <pre><code>import matplotlib.pyplot as plt
plt.subplot(1, 2, 1), plt.imshow(image, cmap='gray')
plt.title('Original Image'), plt.axis('off')
plt.subplot(1, 2, 2), plt.imshow(sobel_combined, cmap='gray')
plt.title('Edge Detected Image'), plt.axis('off')
plt.show()</code></pre>
</ol>

<h2 id="example-output">Example Output</h2>
<p>The result of applying the Sobel operation is an image that highlights edges, with high-gradient regions showing object boundaries within the original image.</p>

<h2 id="explanation-of-sobel-operators">Explanation of Sobel Operators</h2>
<h3>Sobel X Kernel</h3>
<p>Detects vertical edges:</p>
<pre><code>[-1, 0, 1]
[-2, 0, 2]
[-1, 0, 1]</code></pre>

<h3>Sobel Y Kernel</h3>
<p>Detects horizontal edges:</p>
<pre><code>[-1, -2, -1]
[0, 0, 0]
[1, 2, 1]</code></pre>

<h3>Combining Gradients</h3>
<p>The combined gradient magnitude is calculated as:</p>
<pre><code>Gradient Magnitude = sqrt((Sobel_X)^2 + (Sobel_Y)^2)</code></pre>

<h2 id="contributing">Contributing</h2>
<p>Contributions are welcome! Please feel free to submit a pull request.</p>

<h2 id="license">License</h2>
<p>This project is licensed under the MIT License. See the <code>LICENSE</code> file for details.</p>

</body>
</html>
