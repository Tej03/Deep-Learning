# Fruit Maturity Detection
We recently worked on this deep-learning model. We created a model to detect the maturity level of the fruit through the image. We made our own dataset using 5 classes (five different fruits), categorizing them into 3 types: Unripe, Fresh, and Rot. We trained the model with different architectures and got the best accuracy for CNN (Convolutional Neural Networks) architecture. We tried changing the number of dense layers, convolutional layers, max-pooling layers and epoch values to gain maximum accuracy. We received an accuracy of 90.24% after testing the model. 

## INTRODUCTION

Due to the presence of various vitamins, accessibility, and feasibility of the fruits, they have always had a major contribution to human health and nutrition. There are some nutrients that only fruits can provide such as vitamin C, potassium, and folate. The major constituent responsible for the favourable illustration of fruits is their quality. However, according to the UN, almost 50% of the fruits and vegetables harvested globally are squandered every year due to the lack of proper storage. Therefore, there should be a method to determine the maturity level of harvested crops. The basic measure of quality for most of the fruits is their maturity. Also, harvesting during the proper maturity period is one of the main constraints for determining the quality and shelf life of the fruits. Recognizing the ripeness of fruits by humans is a wearisome, labour-intensive, expensive, error-prone, difficult, and sluggish task. Therefore, a mechanized system of fruit and its ripening detection is essential. This will reduce the manpower and time taken for such tasks. It will also improve the accuracy of the task and remove any chances of human error. 
The fruit quality relies upon the fruit images that illustrate various characteristics like appearance, texture, and dimensions of the fruit. Colour is the major attribute to differentiates the maturity of various fruits like apples, papayas, bananas, tangerines, mangoes, pears, and oranges. For example, oranges are green when they are unripe and turn orange when they are ripe. The same is the case with papaya as it is green and turns yellow when it is ripe.
The discernible properties of these fruits are utilized to predict their maturity, which is forecasted by their colour, size, texture, and shape. This recognition process is achieved utilizing a visual examination, based on knowledge of the color, size, and texture. This research work focuses on distinguishing the fruits according to their maturity, considering the unripe, fresh, and rotten stages of the given fruits: red apple, papaya, pear, cherry, and orange. So here, using convolutional neural networks (CNN) algorithm. 
This work demonstrated the viability of our point of view by using a dataset containing 9997 images of five fruits, to build a model that can be implemented to recognize 3 classes of ripening status. We have created the dataset by extracting images using the OpenCV library from the videos we have captured. We have also used some images from the dataset fruit-360 mentioned in the [4]. We have segregated the images of a single fruit into three categories: unripe, fresh, and rot.    

In paper [4] authors have introduced a dataset Fruits-360 which contains various images of fruits but they are only segregated based on the type of fruit and not on their level of maturity or ripeness. They have also trained a deep neural network that could identify fruits. The fruits were sorted based on the type. We have used images of fruits from dataset Fruits 360 and segregated them according to their ripeness. In paper [1], authors have used modified VGG-16 to classify papaya into three categories: mature, partially mature, and immature. The dataset presented in this was very small. In paper [2] authors have tried to combine RGB and NIR multi-model images inside a DCNN framework for fruit detection.

##  METHODOLOGY

###	Dataset
We have used the Fruits-360 dataset by extracting images from recording videos of fruits. The images from the **Fruits-360** dataset were not annotated or segregated according to the ripeness or maturity but instead according to the type of fruit. The dataset did not contain the images for all the 3 stages of every fruit so we captured and added them to the existing dataset. The videos were captured under proper illumination and plain white background. After recording, the video frames were extracted from the videos. We have used the OpenCV python library to extract frames from the video. After extracting the videos, we removed the background, reduced the noise from the images, and then cropped the image to focus on the fruit for better feature extractions. The preprocessing of images is depicted in Fig 1. The training dataset contains a total of **9997 images** of 5 different types of fruits which include _orange, pear, cherry, apple, and papaya_. There are a total of **15 classes** as we have divided each fruit into 3 categories: 
1.	Unripe
2.	Ripe/Fresh
3.	Rot


	![image](https://github.com/Tej03/Fruits-Maturity-Detection/assets/82440905/a8b1f974-b558-4e3f-ad9d-80d4263388d8)      ---->      ![image](https://github.com/Tej03/Fruits-Maturity-Detection/assets/82440905/40b0b927-e0b8-49cd-ac9e-463cda931f93)       ----->        ![image](https://github.com/Tej03/Fruits-Maturity-Detection/assets/82440905/774a137d-8279-47de-9952-79f8a1e1e9b4)






					

  


					
	
Fig. 1: a) Frame extracted from video, b) Image after cropping, c) Image after removing the background


Fig. 2 presents the sample images from the dataset. We have split the dataset as 80 percent and 20 percent for training and testing purpose.  





![image](https://github.com/Tej03/Fruits-Maturity-Detection/assets/82440905/11f05168-d7b5-4117-a5c5-869a7275b1b0)





Fig. 2: Sample fruit images from the dataset
a)  Unripe Pear, b) Ripe Pear, c) Rot Pear, d) Unripe Cherry, e) Ripe Cherry, f) Rot Cherry



### Architecture 

The purpose of the work is to replicate the human vision in a CNN-based architecture which is proficient in segregating the fruit and its maturity stage just by examining a picture of it. After analyzing the literature, we have used a Sequential model of 10-layer convolutional neural network as shown in Fig 3. The neural network structures we are using consists of 3 convolutional layers intertwined with 2 max pooling layers. The output layer succeeds the last max-pooling layer which consists of one dropout layer, one flatten layer and four dense layers to reduce the dimensions and execute the maturity stage grading for the fruit. Using the Dropout layer, the number of neurons in this hidden layer was minimized to reduce overfitting. We have used total of 4 dense layers after implementing the flattening layers. The first dense layer, consisting of 5000 neurons, takes flattened image input from the preceding max-pooling layer. Successively, two more dense layers are implemented with 1024 and 512 neurons respectively. In the end, to predict each category of the fruits, a dense layer with 15 neurons was utilized as the output layer. In Table 1 we present the model configuration.



![image](https://github.com/Tej03/Fruits-Maturity-Detection/assets/82440905/9413b89c-98b9-4daa-975a-9fc81ccccd54)


Fig 3: 10-layer convolutional neural network Architecture of the model


Table 1: Model configuration

![image](https://github.com/Tej03/Fruits-Maturity-Detection/assets/82440905/fce15c68-3049-4c3b-9731-aafd1141315c)

 
 
