# Crop Disease Detection and Notification System

## Project Overview

This project is a crop disease detection system designed to assist farmers by detecting diseases in cotton crops through images taken in the field. The system uses object detection and image classification models to identify crop diseases and provide recommendations for pest control. Upon detecting a disease, the system sends push notifications to farmers, prompting them to take action. Farmers can then take a picture of the affected area, upload it to the system, and receive a diagnosis of the disease and suggested pesticide treatments.

The project is deployed on a Flask server, where the machine learning models for object detection and image classification are hosted. The system uses YOLOv8 for object detection, along with deep learning models like CNN, VGG16, and MobileNet for disease classification. 

## Key Features

- **Real-time Disease Detection**: YOLOv8 is used for detecting diseases in cotton crops through images uploaded by farmers.
- **Push Notification System**: Upon detecting a disease, a push notification is sent to farmers.
- **Image Classification**: Farmers can upload images of affected crops, and the system classifies the disease and recommends appropriate treatments.
- **Transfer Learning**: The project leverages pre-trained models such as VGG16 and MobileNet to fine-tune and improve the performance on crop disease classification.
- **Flask Deployment**: The models are deployed on a Flask server, allowing easy interaction through a web interface or API.

## Technologies Used

- **YOLOv8**: Object detection framework used for disease detection in images.
- **Deep Learning Models**:
  - **CNN (Convolutional Neural Networks)**: Used for disease classification based on image input.
  - **VGG16**: Pre-trained model fine-tuned for disease classification.
  - **MobileNet**: Lightweight pre-trained model used for efficient disease classification.
- **Flask**: Python web framework used for deploying the model as a web application.
- **Push Notification**: A notification service to alert farmers when diseases are detected.
- **TensorFlow, Keras**: Deep learning frameworks used for training and inference.

## Data Sources

- **Kaggle**: Image dataset for cotton crop diseases.
- **Roboflow**: Pre-processed dataset for object detection tasks.

## Installation and Setup

Follow these steps to set up and deploy the project:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/whoisusmanali/AgriTopShot.git
   cd AgriTopShot
   ```

2. **Install Dependencies**:
   Create a virtual environment and install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Download Datasets**:
   - Download the dataset from Kaggle and Roboflow.
   - Place the dataset in the `data/` directory as specified in the project.

4. **Run the Flask Server**:
   After setting up the environment, run the Flask server:
   ```bash
   python app.py
   ```
   This will start the server locally on `http://127.0.0.1:5000/`.

5. **Push Notification Configuration**:
   To enable push notifications, configure the notification API (e.g., Firebase Cloud Messaging) in the `config.py` file. Provide the necessary API keys and credentials.

## Usage

Once the server is running, you can interact with the application via the following routes:

1. **Disease Detection**: Upload an image of the cotton crop to detect diseases.
   - **Endpoint**: `POST /detect_disease`
   - **Request**: Upload an image through the web interface or API.
   - **Response**: JSON with disease detection results, including the disease type and location.

2. **Disease Classification**: Upload an image to classify the disease and get recommendations.
   - **Endpoint**: `POST /classify_disease`
   - **Request**: Upload the image of the crop.
   - **Response**: JSON with disease classification, including the disease name and recommended pesticide.

3. **Push Notification**: A push notification is sent to the farmer upon detection of a disease.
   - Ensure the notification service is correctly set up to send notifications to registered devices.

## Example API Request

To classify a disease via the Flask API:

```bash
curl -X POST -F "image=@/path/to/cotton_crop_image.jpg" http://127.0.0.1:5000/classify_disease
```

The response will contain the classification results:

```json
{
  "disease": "Cotton Leaf Curl Virus",
  "recommended_pesticide": "Pesticide A",
  "confidence": 0.92
}
```

## Contribution

Feel free to contribute to the project by forking the repository and submitting pull requests for bug fixes, enhancements, or new features. If you find any issues, please open an issue, and I will address it promptly.


## Some Predictions:
<img width="1470" alt="Screenshot 2024-01-06 at 12 46 10 PM" src="https://github.com/whoisusmanali/AgriTopShot/assets/104086680/d4178625-3a0e-4225-bf78-7662a753f6c3">


<img width="1470" alt="Screenshot 2024-01-06 at 12 44 50 PM" src="https://github.com/whoisusmanali/AgriTopShot/assets/104086680/ed9a21c5-e2bd-47d3-9868-b612ce8ebf7b">
