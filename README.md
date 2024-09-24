# Rekognize My Photos

This repository implements a photo recognition system that leverages **AWS Rekognition** to analyze and label images automatically. The project allows users to upload images and get detailed information such as object labels, facial recognition, and scene description using Amazon's powerful image recognition API.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Overview

Rekognize My Photos uses **AWS Rekognition** to automatically detect objects, faces, scenes, and text within images. The system can be integrated into applications where photo management and recognition are required, providing detailed analysis for image-based datasets.

## Features

- **Object Detection**: Automatically detects and labels objects within images.
- **Face Recognition**: Recognizes human faces and provides information such as emotions, age range, and other facial attributes.
- **Scene and Text Detection**: Identifies scenes (e.g., outdoors, indoors) and detects text within the images.
- **AWS Rekognition API Integration**: Utilizes the full capabilities of AWS Rekognition for analyzing image content.

## Installation

### Prerequisites

Before running the project, ensure you have the following:

- **AWS Account** with access to AWS Rekognition.
- **AWS CLI** configured with your credentials.
- Python 3.x
- Boto3 (AWS SDK for Python)
  
### Steps

1. Clone the repository:

    ```bash
    git clone https://github.com/simarmehta/RekognizeMyPhotos.git
    cd RekognizeMyPhotos
    ```

2. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

    *(If `requirements.txt` is missing, manually install dependencies: `pip install boto3`)*

3. Set up your AWS credentials with the AWS CLI:

    ```bash
    aws configure
    ```

4. Ensure that the Rekognition service is enabled in your AWS account and your user has appropriate permissions.

## Usage

1. To analyze an image, run the main script with the image file path:

    ```bash
    python rekognize_my_photos.py --image_path <path_to_image>
    ```

2. The script will upload the image to AWS Rekognition, process it, and return detailed information about objects, faces, and other elements within the image.

3. The output will display the recognized labels, objects, facial attributes, and any detected text.

## How It Works

1. **Image Upload**: The image is uploaded to AWS Rekognition using the **Boto3** library.
2. **Rekognition Analysis**: AWS Rekognition processes the image and returns detailed metadata, including:
   - **Objects**: Detected objects in the image, with confidence scores.
   - **Faces**: Recognized human faces, with attributes such as emotions, gender, and age range.
   - **Text**: Any text present within the image is detected and extracted.
3. **Output**: The script prints the recognized labels and data, along with the confidence levels for each detected element.

### Key Libraries and Tools:
- **Boto3**: AWS SDK for Python, used for accessing AWS Rekognition API.
- **AWS Rekognition**: Cloud-based image analysis service to extract insights from images.

## Project Structure

```bash
RekognizeMyPhotos/
├── rekognize_my_photos.py  # Main script to analyze photos using AWS Rekognition
├── utils/                  # Helper functions for processing and AWS interactions
├── data/                   # Sample images (optional)
├── requirements.txt        # Required Python libraries
└── README.md               # Documentation
