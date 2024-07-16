# Pepsi-Coke-LogoDetection

## Objective
This project sets up an ML pipeline that:
1. Takes a ```video``` file as input.
2.  Uses the ```av``` Python library to extract video frames and their timestamps.
3. Utilizes a pre-trained/custom-trained ```YOLOv8``` model to detect Pepsi and CocaCola logos in the video.
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


## Version-1: ```Pre-trained``` YOLOv8 Model for Inference

### Methods involved:
We used a pre-trained YOLOv8 model for detecting Pepsi and Coca-Cola logos in a video. This method involves leveraging an already trained YOLOv8 model to perform object detection directly on video frames extracted from the input video.

### Advantages:

- #### Time Efficiency
- #### Resource Efficiency
- #### Reduced Computational Requirements
- #### No Need for Large Datasets
- #### Generalization:
The pre-trained model has been trained on diverse datasets, which helps in achieving good detection accuracy even for logos in various contexts and backgrounds.
- #### Simplified Development:
By using a pre-trained model, we can focus our efforts on other critical aspects of the project, such as frame extraction, timestamping, and integration of the different components into a seamless pipeline.


## Version-2 (Built on top of Version-1):  ```Custom-trained``` YOLOv8 Model for Inference

### Methods involved:
- #### Data Collection and Preparation:
Gather a dataset of images containing Pepsi and Coca-Cola logos. This dataset should be labeled with bounding boxes around each logo.
- #### Model Training:
Use the YOLOv8 architecture to train a model on your labeled dataset. This involves several iterations of training and validation to optimize the model's ability to detect logos accurately in various video frames.
- #### Inference:
Once trained, the custom model can be used for inference. This involves deploying the model to process each frame of the video, detect the logos, and generate timestamps as per your project requirements.

### Advantages:
- #### Improved Accuracy:
A custom trained model can be fine-tuned on specific data relevant to your application, leading to higher accuracy compared to generic, pre-trained models that might not be optimized for your exact use case.
- #### Tailored to Specific Requirements:
You have control over the training data, allowing you to focus on characteristics and variations that are important for your application. This customization helps in better handling of variations in lighting, angles, backgrounds, etc., which are crucial for logo detection in videos.
- #### Better Generalization:
By training on data that closely matches real-world scenarios, the model can generalize better to unseen data. This means it can perform well on new videos or environments that were not explicitly part of the training set.
- #### Flexibility and Adaptability:
Custom models can be iteratively improved and adjusted based on performance feedback. You can continuously refine the model to achieve better results as you gather more data and insights into its performance.
- #### Privacy and Security:
Training a custom model can be done using proprietary or sensitive data internally, ensuring data privacy and compliance with regulations. This can be crucial for applications where data confidentiality is paramount.
- #### Domain-Specific Knowledge:
Training your own model allows you to incorporate domain-specific knowledge and insights into the model architecture and training process, leading to more effective solutions for your specific problem.
- #### Educational and Research Benefits:
Building and training a custom model provides valuable learning experiences and insights into machine learning and deep learning techniques. It can also serve as a basis for further research and development in related areas.
