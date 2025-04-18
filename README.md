# UNO Card Detection System

This project provides an intelligent UNO card detection and classification system using computer vision techniques. It incorporates real-time detection, template matching, and HSV-based color recognition to classify UNO cards effectively.

---

## Table of Contents
- [Features](#features)
- [Getting Started](#getting-started)
- [How It Works](#how-it-works)
- [Interface and Usage](#interface-and-usage)
- [Folder Structure](#folder-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- **Real-time UNO card detection** via webcam or pre-recorded video streams.
- **Template matching** to identify and classify cards like numbers, action cards, and wild cards.
- **HSV-based color detection** to recognize card colors (red, blue, green, yellow).
- Simple and intuitive interface for card detection.

---

## Getting Started

Follow these steps to set up the UNO Card Detection system:

### Prerequisites
Ensure you have Python 3.7 or later installed and the following libraries:
- `opencv-python`
- `numpy`
- `matplotlib`

Install the required libraries:
```bash
pip install opencv-python numpy matplotlib
```

---

## How It Works

### Step 1: Template Matching
The system uses pre-cropped templates of UNO cards to match against the detected regions of interest (ROI). Templates are grayscale images that represent individual card types. The matching process involves:
1. Loading pre-cropped card templates.
2. Identifying contours in the captured frame to extract potential card regions (ROI).
3. Matching the ROI with the templates using OpenCV's `cv2.matchTemplate` function.

### Step 2: HSV-Based Color Detection
The HSV (Hue, Saturation, Value) color model is used to identify the colors of the cards from the webcam feed. Each color has a predefined range of HSV values:
- Red
- Blue
- Green
- Yellow

### Step 3: Real-Time Detection
The detection pipeline involves:
1. Capturing frames from a live webcam feed.
2. Detecting contours and extracting ROIs.
3. Matching ROIs with templates.
4. Highlighting detected cards with bounding boxes and labels.

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

### Real-time Detection
1. Start the detection system as described above.
2. Position UNO cards in front of the webcam.
3. Detected cards will be highlighted with bounding boxes and labels indicating their color and type (e.g., `red_5_card`, `wild_plus_4_card`).

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
├── README.md                # Project documentation
└── requirements.txt         # Python dependencies
```

## Demo Video

https://www.youtube.com/watch?v=sa3NrbzPAWQ
