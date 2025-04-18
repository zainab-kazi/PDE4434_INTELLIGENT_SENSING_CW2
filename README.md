# UNO Card Detection System

This project provides an intelligent UNO card detection and classification system using computer vision techniques. It incorporates real-time detection, template matching, HSV-based color recognition, and object classification. It also supports model training for enhanced detection accuracy.

---

## Table of Contents
- [Features](#features)
- [Getting Started](#getting-started)
- [How It Works](#how-it-works)
- [Training the Model](#training-the-model)
- [Interface and Usage](#interface-and-usage)
- [Folder Structure](#folder-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- **Real-time UNO card detection** via webcam or pre-recorded video streams.
- **Template matching** to identify and classify cards like numbers, action cards, and wild cards.
- **HSV-based color detection** to recognize card colors (red, blue, green, yellow).
- **Model training framework** to improve classification accuracy.
- Generated YOLO-compatible labels for advanced model training.

---

## Getting Started

Follow these steps to set up the UNO Card Detection system:

### Prerequisites
Ensure you have Python 3.7 or later installed and the following libraries:
- `opencv-python`
- `numpy`
- `matplotlib`
- `scikit-learn`
- `albumentations`

Install the required libraries:
```bash
pip install opencv-python numpy matplotlib scikit-learn albumentations
```

---

## How It Works

### Step 1: Template Matching
The system uses pre-cropped templates of UNO cards to match against the detected regions of interest (ROI). Templates are grayscale images that represent individual card types.

### Step 2: HSV-Based Color Detection
The HSV (Hue, Saturation, Value) color model is used to identify the colors of the cards from the webcam feed. Each color has a predefined range of HSV values.

### Step 3: Training the YOLO Model
The system generates YOLO-compatible labels for UNO cards based on their color and type. These labels can be used to train a YOLO model for object detection.

### Step 4: Real-Time Detection
The detection pipeline involves:
1. Capturing frames from a live webcam feed.
2. Identifying contours and extracting ROIs.
3. Matching ROIs with templates.
4. Highlighting detected cards with bounding boxes and labels.

---

## Training the Model

The project supports generating YOLO-compatible labels and training machine learning models for improved card detection. Follow these steps:

1. **Prepare the Dataset**:
   - Organize UNO card images in the `dataset/` folder, grouped by color (`red`, `blue`, `green`, `yellow`, `wild`).

2. **Generate YOLO Labels**:
   - Use the provided scripts in the notebook to create YOLO-compatible `.txt` labels for each card.
   - Labels are automatically generated for `train/`, `test/`, and `val/` subsets.

3. **Train the YOLO Model**:
   - Use the generated labels and images to train a YOLO model.
   - Tools like [YOLOv5](https://github.com/ultralytics/yolov5) or [YOLOv8](https://github.com/ultralytics/ultralytics) are recommended for training.

4. **Update the Detection Script**:
   - Replace the template-matching logic with the YOLO model for enhanced detection accuracy.

---

## Interface and Usage

### Template Matching
1. **Prepare Templates**:
   - Use the cropping script in the notebook to generate templates for all card types.
   - Place the generated templates in the `templates/` folder.

2. **Run the Detection System**:
   - Open the `uno.ipynb` notebook.
   - Execute the cells to load templates and start the detection pipeline.
   - The system will classify detected cards and display results in a live video feed.

### YOLO-Based Detection
1. Train the YOLO model as described in the [Training the Model](#training-the-model) section.
2. Replace the detection logic in the notebook with the YOLO model.
3. Run the updated detection pipeline for real-time results.

---

## Folder Structure

The system is organized as follows:
```
PDE4434_INTELLIGENT_SENSING_CW2/
├── uno.ipynb                # Main Jupyter Notebook
├── templates/               # Pre-cropped UNO card templates
├── dataset/                 # Raw images of UNO cards
│   ├── blue/
│   ├── red/
│   ├── green/
│   ├── yellow/
│   └── wild/
├── labels/                  # YOLO-compatible labels
├── README.md                # Project documentation
└── requirements.txt         # Python dependencies
```

---

## Contributing

Contributions are welcome! Feel free to fork the repository, create a feature branch, and submit a pull request.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

## Acknowledgments

Special thanks to:
- The OpenCV and Python communities for their excellent libraries.
- The creators of YOLO for their robust object detection framework.
- The course `PDE4434 Intelligent Sensing` for inspiring this project.
