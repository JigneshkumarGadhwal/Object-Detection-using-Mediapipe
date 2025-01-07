# Object Detection with MediaPipe

This project demonstrates how to perform object detection using MediaPipe's **EfficientDet model** in a Python environment. The system detects objects in an image, visualizes bounding boxes around the detected objects, and displays the labels along with their confidence scores.

## Prerequisites

To run this project, you need to install the following Python libraries:

- **OpenCV**: For image manipulation and visualization.
- **NumPy**: For array manipulation.
- **MediaPipe**: To leverage the pre-trained object detection models.

Install the required dependencies using:

```bash
pip install opencv-python numpy mediapipe
```

## Features

- **Efficient Object Detection**: Uses a pre-trained EfficientDet Lite2 model to detect objects in images.
- **Bounding Boxes**: Visualizes bounding boxes around detected objects.
- **Detection Labels**: Displays the labels of detected objects with their associated confidence scores.
- **Image Visualization**: Uses OpenCV to display the input image with annotated bounding boxes and labels.

## File Structure

```
.
├── object_detection.py             # Python script to detect and visualize objects in images
└── README.md                       # Project documentation
```

## How It Works

1. **Model Setup**: The EfficientDet Lite2 model (in `.tflite` format) is used for object detection. The model is loaded using MediaPipe's Python API.
2. **Object Detection**: The model detects objects in a given image. Detected objects include bounding boxes, labels, and confidence scores.
3. **Visualization**: Bounding boxes are drawn around detected objects, and the label with the confidence score is displayed next to each box.
4. **Result Display**: The input image with bounding boxes and labels is displayed using OpenCV.

### Code Breakdown

- **Model Initialization**: The `BaseOptions` class initializes the model path, which is the location of the pre-trained EfficientDet model.
- **Detection Process**: The `ObjectDetector` class from MediaPipe performs the detection. The model returns a list of detections, each containing bounding box coordinates and category names.
- **Visualization**: The `visualize()` function processes the detections by drawing bounding boxes and appending labels and confidence scores.

### Model Options

You can modify the options passed to the detector, including:

- **score_threshold**: The minimum score for detected objects (set to `0.5` in the example).
- **category_allowlist**: You can specify which categories to allow for detection.
- **category_denylist**: You can exclude specific categories.

## Usage

1. **Prepare the Image**: Ensure that you have an image file for detection. Modify the `image_path` variable in the script to point to your image file.
   
2. **Run the Script**: Execute the Python script to perform object detection and visualization:

```bash
python object_detection.py
```

3. **View Results**: The input image will be displayed with bounding boxes and labels showing detected objects and their confidence scores.

4. **Exit**: Press any key to close the image window after the detection results are displayed.

## Example Image

The model detects an object using an image, such as people, animals, or vehicles, depending on the pre-trained model's capabilities.

## Notes

- Ensure that the `model_path` variable is correctly set to the location of your `.tflite` model file.
- You can use other trained models provided by MediaPipe for different object detection tasks.
- The image input is read using MediaPipe's `mp.Image.create_from_file()` method.

