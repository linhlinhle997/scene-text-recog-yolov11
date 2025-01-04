# Scene Text Recognition (STR) with YOLOv11 and CRNN

This project implements Scene Text Recognition (STR) using a two-step pipeline:

1. **Text Detection** with YOLOv11.
2. **Text Recognition** with a CRNN model.

The program leverages the **ICDAR2003** dataset, converting it into the YOLOv11 format and extracting individual text images for CRNN training.

## Project Structure

The project is organized into three main notebooks:

- **`detection.ipynb`**: Handles text detection using YOLOv11.
- **`recognition.ipynb`**: Handles text recognition using a CRNN model.
- **`str_full_pipeline.ipynb`**: Combines detection and recognition models into a full STR pipeline.

## Dataset

The project uses the ICDAR2003 dataset. Download and extract the dataset as described in the notebook.

## Usage

1. Detection
Run the `detection.ipynb` notebook to train the YOLOv11 model for text detection. After training, you will obtain the best-performing model (`best.pt`) for detecting text regions in images.

2. Recognition
Run the `recognition.ipynb` notebook to train the CRNN model for text recognition. The model will take cropped text regions (extracted by YOLOv11) and recognize the text content. The resulting model will be saved as `ocr_crnn.pt`.

3. Full Pipeline
Run the `str_full_pipeline.ipynb` notebook to integrate the trained YOLOv11 and CRNN models into a complete STR pipeline. The notebook will automatically detect text regions in an image using `best.pt` (from detection) and recognize the text using `ocr_crnn.pt` (from recognition).

## Results

The final output will visualize the results with bounding boxes around detected text regions and the recognized text printed on the image.