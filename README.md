Introduction

–	Our project revolves around the autonomous driving topic specifical object detection.
–	Object detection is an important aspect of autonomous driving, the realm of automated driving will rely heavily on mapping the environment surrounding the machines. So, it would mean that the vehicle will have a well detail map of the environment of the vehicle. This is crucial for safety in public spaces, abiding by traffic laws, and identifying obstacles.
–	In this report we are presenting a great way to achieve this very crucial part of autonomous driving. Using the well annotated and customizable dataset of COCO, with the CNN model of YOLO we are able to make a fast and reliable system that can be implemented into vehicles and allow for a more detailed mapping of its environment. 

Technologies 

–	When it comes to object detection in autonomous driving we think about 360 cameras, LiDAR, Radar, sensors, etc. All of these technologies are great at mapping the environment but they are fully able to recognize what is it that they are sensing or mapping. On the other hand, a machine learning model like YOLO is able to put a class on each of the detect object so give a more detail map. 
•	YOLO is one of many models in the field of object-+ detection, others include R-CNN (Fast/Faster), Haar Cascades, and SSD (Single Shot Detector). What distinguishes YOLO above most is:
•	Speed: YOLO’s model allows for real time processing, processing images quickly is due to its one stage detectors, unlike others who use two stage detectors and require more processing time.
•	Simple: The single neural network reduces the computational burden and simplifies the training processes; this allows for a simple pipeline for data. 
•	Accuracy: Over the years YOLO has seen significant improvements to become a highly competitive object detection model. Some of the improvement seen with v5 is model sparsity (pruning) and automatic learning rate scheduling, this has made the model robust and versatile in different scenarios. 
–	Recent Developments:
•	YOLO has many improvements such as YOLOv9 such focusses on better accuracy by creating a better network architecture to optimize and enhance the process for better results.
•	Other developments include 3D object detection improvements using 3D LiDAR images and 2D RGB images to give a more detail 3D mapping of the surrounding (Ritsumeikan University Paper Japan).
•	Deep Learning systems is the next major development to as it becomes better all the models will only become better with it. This will yield more sophisticated object detection models.

Project Methods

–	COCO dataset set containing 330,000 images for training and validation.
•	The common objects in context dataset (COCO) is an impressive large scale object detection, segmentation, and bounding dataset. This makes it a create tool for training models for object detection since it includes images with a wide variety of objects from everyday scenes with many objects. 
•	COCO annotation: these annotations include object bounding boxes and segmentation masks, they are contained in JSON format with details including the class, location, segmentation of each object. This formatting aspect can be important depending on the model.
–	Model YOLOv5:
•	YOLO object detection model for quick object detection. Pre-processing setup includes reformatting the dataset to a text file to be acceptable to the YOLO model. Training configuration include resizing to a uniform size image (640x640 pixels). For our training setting we experimented with different settings and came to the conclusion to use the below. This includes 640 pixels, epochs of 50 which can be dropped further but we found 50 to be appropriate to achieve high accuracy, as we increase the images used in our dataset, we can lower this to achieve faster speeds. We kept our batch at 16 to ensure we have a complex batch with overwhelming the model and to ensure acceptable speeds. Our Yaml file included the training and validation directories as well as the number of classes included, we also have our default weights of the Yolo model, which was updated after training on the COCO images.
–	Results:
•	Initially are results showed great accuracy with detected objects, but would forget to detect and label object. After investigating it we found this had to main reason one was to image in the train dataset included such image or angle of object in said images, or it was to far and the images had close up objects. This was overcome by increasing the dataset size and lower the batch amount as well as increase the epoch to ensure the model was able to fully digest the images over a decent number of times. As we increased the dataset, batch, and epoch we seen better results, which we found acceptable.
