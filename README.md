# Flood-Detection
A ML model that predicts if an area is flooded or not.
Predicting floods for disaster aid

Abstract

Water related natural disasters are an imminent threat for many. Homes are destroyed, infrastructure is damaged, people are displaced and are in need for resources. In Louisiana, hurricanes are an annual threat; ergo the necessity for predicting the areas susceptible to flooding. In this multi-model program, I compared images before and after flooding to compare the dissimilarity between them. To train my model I will be using Fast.ai’s vision_learner module which defines a convolution neural network (CNN).

I.	INTRODUCTION
For this project, I was inspired to do my project on a flood predictor system because for one, I am interested in image classification and secondly, I have family in the city of New Orleans which gets about 64 inches of rain annually. In the case of a natural disaster such as a hurricane, detecting if an area is flooded or not is important for the first responders, the information they receive aids them with figuring out the resources they need. This project idea sparked my interest because I like the idea of a machine learning model determining something based on an image. Other methods for flood prediction have also been in practice, for example, To aid in flood detection, drones have been of great importance. “Drones equipped with sensors and latest algorithms (e.g., computer vision and deep learning) have emerged as a potential platform which may be useful for flood monitoring, mapping and detection activities in a more efficient way than current practice.”[1]. In this project, I am going to use Fast.ai’s libraries to build a machine learning model which can predict if a given area is flooded or not. This model will aid in the forefront of using A.I. to solve challenging problems caused by natural disasters.

II.	THEORY  OR RELATD WORKS 
For my data analysis, I used Fast.AI.s Vision_learner module which is a convolution neural network. This CNN was vital for training my model and getting accurate predictions .Fast.ai’s CNN uses resNet-18 which is a convolutional neural network that is 18 layers deep. You can load a pretrained version of the network trained on more than a million images from the ImageNet database.

III.	MATERIALS AND METHODS  

A. Data explanation and characterization  

My data is sourced from Kaggle[2] and consists of 322 images. These images are a make up of Twenty parishes in Louisiana—Acadia, Ascension, East Baton Rouge, Livingston, Avoyelles, Evangeline, East Feliciana, West Feliciana, Iberia, Iberville, Jefferson Davis, Lafayette, Pointe Coupee, St. Helena, St. Landry, St. Martin, St. Tammany, Washington, Tangipahoa, and Vermillion—were declared major federal disaster areas. The size of my data in total is 98.31 MB. 

B. Data preprocessing  

	During this step I did not have to do much since I was dealing with images only. What I did is split the data into separate folders in the beginning ‘0’ for training data and ‘1’ for my validation data, and the split was (270, 52). After that I ensured all the images were sent to their proper folder by moving them to new directories folder ‘0’ and folder ’1’.
  
C. Data  analysis/mining

	For training my model, I used Fast.ai’s resnet18, a CNN that is 18 layers deep and has a default learning rate of 0.1 and decays by a factor of 10 every 30 epochs. For my project, I chose to run the CNN with 20 epochs the first time and the second time after reoptimizing the CNN. The results of the first CNN showcased that my model no longer improves after the 16th epoch. The train_loss does not decrease any further, valid_loss has no significant change, and error_rate has no change at all. I chose 20 epochs due to the small data size and the assumption that the CNN would learn my images quickly. Before I mention the second CNN, it’s important to know about my confusion matrix and my model evaluation. My confusion matrix had minimal misclassifications with a total number of 3( Will show results). For my model evaluation, my model was able to predict most images as flooded or not flooded with the percentage of the area covered with water. So, I wanted to try on photos outside the trained images from the dataset to see how my model would perform. My findings indicate that even images taken from a helicopter point of  view can still be predicted with great accuracy as flooded or not flooded thought there were some misclassifications. Finally, I optimized my CNN by increasing the batch size to 32 which increased the model’s accuracy.

IV. RESULTS  

![image](https://user-images.githubusercontent.com/47839751/234985058-1aac3236-a324-402d-96fe-980a6a9a87c5.png)

Figure 1:  Confusion matrix

![image](https://user-images.githubusercontent.com/47839751/234985132-e77d3564-59cc-4177-a37d-51ba63396d64.png)	

Figure 2: Showcasing model performance on images in dataset(1,2,3,5) and outside of dataset(4,6,7,8)
 
![image](https://user-images.githubusercontent.com/47839751/234985212-863919e5-5681-412c-a135-f582d9b534cf.png)
 
Figure 3. First CNN 

![image](https://user-images.githubusercontent.com/47839751/234985312-0245d82e-2ef9-4291-bb57-0b4bdf2c9959.png)

Figure 4. Second CNN after optimizing.

![image](https://user-images.githubusercontent.com/47839751/234985407-fb4c64c5-0ebe-4826-b9bf-9fe5a89417e1.png)
 
Figure 5. Image flood probability before testing again.
 
![image](https://user-images.githubusercontent.com/47839751/234985487-de6a13db-a911-476a-b2b7-309eaeefb617.png) 
 
Figure 6. Testing image again after optimizing CNN 

IV.	DISCUSSION AND CONCLUSION 
Overall, I noticed that since all the images in the training set are top-down view, the model did not perform well with images closer to the ground. Though some images close to the ground did perform well before the model was optimized, most did not perform so well. After optimization, the model could predict the photos closer to the ground more efficiently. Additionally, If the model were originally trained with images closer to the ground, there would be no need for optimization if it performed well already.


