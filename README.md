# PDE4434_INTELLIGENT_SENSING_CW2
# UNO Card Recognition

This project is designed to recognize UNO cards using a webcam or an image file. The project includes data collection, model training, and card recognition.

## Prerequisites

- Python 3.7+
- Install required libraries using `pip install -r requirements.txt`

## Data Collection

To collect images for training the model:

```bash
python collect_data.py
```

Follow the prompts to enter the label of the card (e.g., `red_0`) and the number of images to capture.

## Model Training

To train the model:

```bash
python train_model.py
```

This will train a CNN model using the collected images and save the model as `uno_model.h5`.

## Card Recognition

To recognize cards:

### From an Image File

```bash
python uno_card_recognition.py
```

Follow the prompts to enter the path to the image file.

### From a Camera Feed

```bash
python uno_card_recognition.py
```

Follow the prompts to select the camera mode.

Press `q` to quit the camera feed.

## Notes

- Ensure that the `data/train` directory contains subdirectories for each card label (e.g., `red_0`, `yellow_9`) with the captured images.
- The model expects images of size 150x150 pixels.
