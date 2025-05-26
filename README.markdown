# Image Processing Project

## Project Overview
This Python-based image processing project implements a pipeline using OpenCV and NumPy to perform brightness/contrast adjustment, Gaussian blur, Non-local Means Denoising, Canny edge detection, and SIFT feature extraction. Designed for Google Colab, it supports `.jpg`, `.png`, and `.tif` image formats, includes robust error handling, and follows PEP 8 guidelines. Processed images are displayed inline and saved for download.

## How to Run the Code
1. **Prerequisites**:
   - Google Colab environment with internet access.
   - Install required libraries by running:
     ```bash
     !pip install opencv-python numpy
     ```
2. **Setup**:
   - Create a new Colab notebook.
   - Copy and paste the provided cells (markdown and code) into the notebook.
3. **Execution**:
   - Run cells in sequence:
     1. Install dependencies.
     2. Define imports and functions.
     3. Upload an image (.jpg, .png, or .tif) when prompted; it will be saved as `input_image.jpg`.
     4. Execute the processing pipeline to view results inline.
     5. Download the processed images as a zip file.
4. **Input**:
   - Upload an image in a supported format via the Colab file upload prompt.
5. **Output**:
   - Processed images (e.g., `bright_contrast.jpg`, `edges.jpg`) are saved in the `processed_images` directory.
   - Images are displayed inline after each processing step.
   - A zip file (`processed_images.zip`) is created for download.

## Techniques Used
- **Brightness/Contrast Adjustment**: Modifies image intensity using `cv2.convertScaleAbs` with adjustable brightness (-100 to 100) and contrast (0 to 3).
- **Gaussian Blur**: Applies a 5x5 Gaussian filter via `cv2.GaussianBlur` to reduce image detail.
- **Non-local Means Denoising**: Uses `cv2.fastNlMeansDenoisingColored` to reduce noise while preserving edges.
- **Canny Edge Detection**: Detects object boundaries with `cv2.Canny` using low (100) and high (200) thresholds.
- **SIFT Feature Extraction**: Extracts keypoints and descriptors with `cv2.SIFT_create` for object characterization, ready for classification tasks.

## Known Limitations
- Input images must be in `.jpg`, `.png`, or `.tif` format; other formats raise an error.
- SIFT feature extraction may be slow for large images due to computational complexity.
- Assumes BGR color format (OpenCV standard) for input images.
- No classification is implemented, but SIFT descriptors are prepared for potential use.
- Colab’s temporary file system requires downloading the output zip to retain results.

## Notes
- Use a sample image from your device or a public source (e.g., OpenCV samples) for testing.
- Adjust parameters (e.g., brightness, kernel size) in the processing pipeline cell if needed.
- Ensure cells are run in order to avoid errors (e.g., `NameError` for undefined `np`).
- For non-Colab environments, modify file handling (e.g., replace `files.upload` with local file paths).