# Pepsi-Coke-LogoDetection

## Objective
This project sets up an ML pipeline that:
1. Takes a video file as input.
2.  Uses the ```av``` Python library to extract video frames and their timestamps.
3. Utilizes a pre-trained ```YOLOv8``` model to detect Pepsi and CocaCola logos in the video.
4. Outputs a ```JSON``` file with timestamps for each detected logo.

## Output Format
The output JSON file will have the following format:
```
{
    "Pepsi_pts": [10.1, 10.2, 10.3, ...],
    "CocaCola_pts": [20.3, 31.8, 40.12, ...]
}
```

## Requirements
1. Python 3.x
2. Google Colab or a local machine with GPU support (optional but recommended for faster execution)


## Dependencies
The following Python packages are required:

- ```av``` for video frame extraction
  
- ```torch``` and ```torchvision``` for the YOLOv8 model
  
- ```opencv-python``` for additional image processing

- ```yolov8``` for the pre-trained YOLOv8 model



## Methods Considered and Why They Were Not Used

### 1. Data Collection

Description: Gathering a comprehensive dataset of images containing Pepsi and Coca-Cola logos.

Reason for Not Using: 
- Time-Consuming: Collecting a large dataset of labeled images is resource-intensive and time-consuming
- Resource-Intensive: Requires significant effort to find and label a sufficient number of relevant images, which can be avoided by using pre-trained models.
- Pre-Trained Models: Leveraging existing pre-trained models allows us to skip this step and directly use a robust solution.

Focus on Pipeline: The assignment's objective is to demonstrate the pipeline setup and functionality, not data collection.

### 2. Data Cleaning
Description: Processing raw data to ensure it is clean and suitable for training or inference.

Reason for Not Using:
- Pre-Processed Data: The frames extracted from the video are assumed to be of good quality, reducing the need for extensive cleaning.
- Pre-Trained Model Usage: Using a pre-trained model mitigates the need for comprehensive data cleaning typically required before training.
- Time Constraints: Given the short duration of the assignment, the focus is on setting up and demonstrating the pipeline rather than preparing the data.
  
Primary Objective: The main task is logo detection and timestamp generation, which does not require extensive data cleaning.

### 3. Training
Description: Training a custom YOLOv8 model on a labeled dataset specific to Pepsi and Coca-Cola logos.
Reason for Not Using:
Computationally Expensive: Training deep learning models requires significant computational power, which might not be readily available.
Pre-Trained Models Available: YOLOv8 pre-trained models are readily available and can be fine-tuned or used directly for our task.

Focus on Inference: The task requires demonstrating logo detection, which can be effectively achieved using pre-trained models.

### 4. Inference
Description: Using a trained model to make predictions on new data.
Reason for Using:
- Core Task: The assignment specifically requires detecting logos in a video and generating timestamps, which is an inference task.
- Efficiency: Using a pre-trained model for inference is efficient and effective, meeting the assignment's requirements within the given timeframe.
- Direct Application: Allows us to focus on the practical application of the model for the specific task without the overhead of training.
Demonstrable Results: Ensures we can provide a functional demo and the required JSON output, fulfilling the evaluation criteria.

By focusing on inference using a pre-trained YOLOv8 model, we efficiently address the assignment's core requirements and deliver a functional solution within the specified timeframe. This approach leverages existing robust models, ensuring high accuracy and performance without the need for extensive data collection, cleaning, or training.


# Conclusion
## Method Used: Pre-trained YOLOv8 Model for Inference
Description: We used a pre-trained YOLOv8 model for detecting Pepsi and Coca-Cola logos in a video. This method involves leveraging an already trained YOLOv5 model to perform object detection directly on video frames extracted from the input video.


### Advantages:

- Time Efficiency
- Resource Efficiency
- Reduced Computational Requirements
- No Need for Large Datasets
- High Accuracy and Performance
- Focus on Pipeline and Integration
- State-of-the-Art Model: YOLOv8 is a state-of-the-art object detection model known for its high accuracy and speed. Using a pre-trained version of this model ensures that we benefit from its robust performance.
- Generalization: The pre-trained model has been trained on diverse datasets, which helps in achieving good detection accuracy even for logos in various contexts and backgrounds.
- Simplified Development: By using a pre-trained model, we can focus our efforts on other critical aspects of the project, such as frame extraction, timestamping, and integration of the different components into a seamless pipeline.
