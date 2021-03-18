FACE-RECOGNITION-USING-PYTHON
Introduction
Face Recognition is a simple project developed using Python.

The project is developed by using Siamese Neural Network Facial recognition has many benefits in society, including increasing safety and security and preventing crimes.

It can even help support medical efforts, in some cases.

It is more convenient than the physical database which provides faster access. This way we can recognize any person faster and without any human intervention.

It uses a webcam to stream frames from a live video to a pre-trained Siamese neural network and using a true image of the user the system is able to authenticate the user in front of the webcam.

We have trained and implemented a robust model that can recognize faces, even when the subject has different expressions and when the photo is taken from different angles.

Program that uses the pre-trained neural network and a webcam, to authenticate the user sitting in front of the computer.

Technical requirements
The following Python libraries are required for this chapter:

Numpy 1.15.2

Keras 2.2.4

OpenCV 3.4.2

PIL 5.4.1

The following files are present in the project:
face_detection.py contains the Python code for face detection using OpenCV.

siamese_nn.py contains the Python code to create and train a Siamese neural network.

get_true_face.py contains the Python code for the onboarding process of the face recognition system.

face_recognition_system.py contains the complete face recognition system program.

helper.py contains the euclidean_distance, contrastive_loss, and accuracy functions needed to train a Siamese neural network.

Please run the Python files in this order:
siamese_nn.py: To train a Siamese neural network for face recognition

get_true_face.py: To start the onboarding process for the face recognition system

face_recognition_system.py: The actual face recognition program that uses your webcam

Facial Recognition Systems
We can break down the face recognition into smaller steps.

Face detection: Detect and isolate faces in the image.

We have used a pre-trained cascade classifier for face detection called Haar Cascades.

Features with alternating regions of dark and light pixels are known as Haar features.

Face recognition: For each detected face in the image, we run it through a neural network to classify the subject.

One-shot learning
Given the unique requirements and constraints faced by facial recognition systems, it is clear that the paradigm of training a CNN for classification using a huge dataset (known as batch learning classification) is unsuitable for the facial recognition problem.

Instead, our objective is to create a neural network that can learn to recognize any face using just a single training sample.

This form of neural network training is known as one-shot learning.

The following tasks should be performed when determining whether the presented face belongs to an arbitrary person (say person A):
Retrieve the stored image of person A (obtained during the onboarding process). This is the true image of person A.

At testing time (for example, when someone is is trying to unlock the phone of person A), capture the image of the person. This is the test image.

Using the true photo and the test photo, the neural network should output a similarity score of the faces in the two photos.

If the similarity score output by the neural network is below a certain threshold (that is, the people in the two photos look dissimilar), we deny access, and if they are above the threshold, we grant access.

The following diagram illustrates this process:

































































