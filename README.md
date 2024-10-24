# CycleGan-for-image-to-image-translation-on-face-sketch-Dataset
![image](https://github.com/user-attachments/assets/4ab81f6a-ab26-42e9-b5f9-3e3823dab776)

This project implements the CycleGAN model based on the original paper for image-to-image translation, specifically focusing on converting face images into sketches and vice versa. The project uses the Person Face Sketches Dataset to train and evaluate the model.
Overview

The objective of this project is to implement a CycleGAN that:

    Converts a real face image into a sketch.
    Converts a sketch back into a real face image.

CycleGAN enables unpaired image-to-image translation without requiring paired examples of input-output data. This allows the model to learn how to perform the translation between two domains using two sets of images: real faces and their corresponding sketches.
Dataset

We use the Person Face Sketches Dataset. The dataset includes:

    Real face images.
    Their corresponding sketch representations.

Model Details

The CycleGAN architecture includes:

    Two generators:
        G1 for converting real face images to sketches.
        G2 for converting sketches back to real face images.
    Two discriminators:
        D1 for distinguishing between real sketches and generated sketches.
        D2 for distinguishing between real faces and generated faces.

Loss functions:

    Cycle-consistency loss ensures that translating a face to a sketch and back to a face results in the original face (and vice versa).
    Adversarial loss to ensure generated images are indistinguishable from real images.

Training

    The model is trained end-to-end using Google Colab for efficient GPU usage.
    We save model weights after every epoch to avoid progress loss. If training is interrupted, it can be resumed from the saved weights.
    The training process is monitored by adjusting hyperparameters such as:
        Learning Rate: Adjusted during training to improve model convergence.
        Batch Size: Dataset is split into batches to avoid memory issues.

Results

The model is capable of performing the following image-to-image translations at test time:

    Sketch to Real Face: Generates a real face from a given sketch.
    Real Face to Sketch: Generates a sketch from a given real face image.
