# **Project: CNN In Real Time** 

In this project, we implement algorithms for **Movements Detection**, **Object Detection** and **Object Tracking**. Our approach involves recognizing movement within the frame, detecting objects, and tracking them in real-time via the camera. We utilize the **ResNet50** model, applying **Transfer Learning** techniques on the **CIFAR-10** dataset, achieving an impressive **accuracy of 95%**.

**Project Overview:** The initial phase of the project focuses on Deep Learning, emphasizing Convolutional Neural Networks and related concepts such as Overfitting, Transfer Learning (including Feature Extraction and Fine Tuning), and importing datasets from binary files. The second phase addresses Computer Vision, employing libraries like **OpenCV** and **NumPy**.

At the outset, we experimented with various models and techniques to identify the best fit for our goal: recognizing birds. Our findings revealed that the ResNet50 model, combined with Transfer Learning and Fine Tuning, yielded the highest accuracy of 95% on the CIFAR-10 dataset.

**Application Architecture:** Next, we developed the application’s front end, which operates between two states: Detection and Tracking. Instead of utilizing the ResNet50 model's predictionsor every frame, we only detect the object once initially, then track it continuously. For instance, processing 2000 frames can differ significantly between executing the model 2000 times versus just once. We also initiate object detection only when movement is detected in the frame, which optimizes performance during static frames.

The process begins with recognizing movement in the frame, after which we isolate the suspicious section and send it to the model for prediction. We use the model’s predictions to identify the object and commence tracking. Once tracking concludes, the application resumes object detection. We log all detection events, recording them with timestamps, and display this information on-screen. Additionally, frames containing detection events are saved in a designated folder, along with a text file detailing all detection occurrences.

**User Interface:** The application features a window divided into six screens:

   1. Main Frame: Displays the live feed from the camera.
   2. Information Frame: Contains detection event summaries and application details.
   3. Tracking Frame: Shows the object’s coordinates, confidence score, prediction time, and frames per second (FPS).
   4. Object Frame: Displays the cropped section sent for prediction.
   5. Scores Frame: Lists the scores for each label.
   6. Mask Frame: Shows the mask applied to the main frame.

The application utilizes **TensorFlow** with **Keras** in **Python**.

Let's see a short video of our application:

https://user-images.githubusercontent.com/107938584/235354576-a6622ecd-53b8-4fc5-bdc5-f8451e8e0203.mp4


Example of folder with the saved frames from detection event:
 
![Detection Event Folder](https://user-images.githubusercontent.com/107938584/212727772-0affb211-d46d-47ed-8bb0-59e195912787.jpg)

Example of the text file with detections events and application information:

![Detection Event txt 2](https://user-images.githubusercontent.com/107938584/212727788-074e1ab1-6b5f-4a0c-8ad0-93f5e316acd4.jpg)


