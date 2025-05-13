
# 🚗 Number Plate Detection using EasyOCR

This project uses EasyOCR along with OpenCV to detect and extract text from images of Indian number plates. The program reads images from a dataset stored in Google Drive, processes each image to detect text, draws bounding boxes around the detected text, and then displays both the processed image and the extracted number plate texts.

---

## 📁 Project Structure

```
number_plate_detection/
├── number_plate_detection.ipynb    # Google Colab Notebook (or Python script)
├── README.md                       # This documentation file
└── Sample_Images/                  # Folder containing number plate images 
    ├── image1.jpg
    ├── image2.png
    └── ...
```

*Note*: The dataset folder is stored in your Google Drive under the path:
`/content/drive/MyDrive/Indian_Number_Plates/Sample_Images`

---

## 🛠️ Requirements

Make sure to install the required libraries using pip. If you are using Google Colab, you can run the installation cell below:

```bash
!pip install easyocr
```

In addition, the project uses:
- OpenCV (`opencv-python`)
- matplotlib
- EasyOCR
- Google Colab patches for image display (`cv2_imshow`)

Install any missing dependencies via pip:

```bash
!pip install opencv-python matplotlib
```

---

## 📌 Dataset

- The dataset consists of images of Indian number plates.
- Ensure that your sample images are stored in the folder:
  `/content/drive/MyDrive/Indian_Number_Plates/Sample_Images`
- Supported image formats include PNG, JPG, and JPEG.

Mount your Google Drive in Colab to access the dataset:

```python
from google.colab import drive
drive.mount('/content/drive')
```

---

## 🔍 How the Code Works

1. **Library Imports and Google Drive Setup**:
   - The code first installs and imports the required libraries.
   - Google Drive is mounted to gain access to the images.

2. **EasyOCR Reader Initialization**:
   - An EasyOCR `Reader` is initialized to detect English text.

3. **Image Processing and Text Detection**:
   - The `detect_number_plate` function reads an image using OpenCV.
   - It processes the image through EasyOCR to find any text.
   - For each detected text, a bounding box is drawn around it, and the text is annotated on the image.

4. **Dataset Analysis**:
   - The `analyze_dataset` function loops through all images in the specified dataset folder.
   - It calls `detect_number_plate` on each image, displays the processed image, and prints out the detected text.
   - The detected texts are stored in a dictionary for summary output.

5. **Visualization**:
   - The processed images are displayed inline in the Colab notebook using `cv2_imshow`.

---

## 🚀 How to Run the Project

1. **Clone or Upload** the project files into your Google Colab environment or local environment.
2. **Mount your Google Drive** to ensure the dataset is accessible:

    ```python
    from google.colab import drive
    drive.mount('/content/drive')
    ```

3. **Install Required Libraries** by running:

    ```bash
    !pip install easyocr opencv-python matplotlib
    ```

4. **Run the Notebook/Script**:
   - Execute the cells in the notebook or run the Python script to process the images.
   - The processed images with detected number plate texts will be displayed along with printed outputs in the console.

---

## ⚙️ Future Improvements

- **Enhanced Preprocessing**: Implement advanced image preprocessing (e.g., filtering and contrast adjustments) to improve OCR accuracy.
- **Support for Multiple Languages**: Extend the detection to include regional languages if necessary.
- **Batch Processing & Saving**: Save the processed images and detection results to disk for further analysis.
- **GUI Improvements**: Develop a simple web interface for interactive use.

---

## 🧑‍💻 Author

This project leverages EasyOCR and OpenCV to facilitate the detection of number plates. It was designed with ease-of-use in mind for educational or prototyping purposes.

---
