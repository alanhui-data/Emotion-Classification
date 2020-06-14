# Emotion-Classification
Realtime Emotion Detection Using mini-Xception and AlexNet

Detailed paper refers to Emotion Classificaion Paper.pdf

Presentation refers to https://www.youtube.com/watch?v=czQRlDtDZs0


## ABSTRACT
Facial emotion recognition (FER) is a popular topic in the computer vision and artificial intelligence areas because of their significant academic and commercial potential. Although facial emotion recognition can be conducted by many methods including multiple sensors, devices and different machine learning algorithms, our project is focusing on applying convolutional neural network (CNN) to process facial emotion recognition from real time video or images and employ a 5-fold cross-validation to evaluate different CNN models with their precision and recall. In our work, we trained and compared two different models, Mini- Xception Model and Alexnet Model, using images from Kaggle facial expression challenge in 2013 [6], and ultimately achieving an accuracy of 75.7% in a seven emotion categories classification test.

## DATA DESCRIPTION
In our work, we used facial expression recognition (FER) dataset from Kaggle challenge in 2013. The data consists of 48×48 pixel grayscale images of faces and it contains 35,888 records in csv format. The csv file contains two columns, "emotion" and "pixels". The "emotion" column contains a numeric code ranging from 0 to 6, inclusive, for the emotion that is present in the image. The emotion and numeric code mapping table is as below.
 
The "pixels" column contains a string surrounded in quotes for each image. The contents of this string are space-separated pixel values in row major order. 

## DATA PRE-PROCESSING

### Imbalance of dataset
Number of disgust image in FER2013 dataset is very small while comparing to other emotions.  With this imbalance dataset, it is impossible for our model to recognize disgust expression.

#### Data Augmentation
AffectNet is a dataset of facial expressions created by Mohammad [7], a CE professor of University of Denver.  It contains more than 1 million facial images either collected from the internet or manually annotated.  Due to storage and network speed limitation, we only able to download 10% of the database.  It contains around 400 disgust images. 
Procedures of data pre-processing:
1.	AffectNet images are color images, we need to convert them into grayscale 
2.	AffectNet images are in different dimensions, we need to resize the image into 48 x 48
3.	Labelling of expression are different, we need to map the expression according to FER2013.


#### Other Augmentation Technique, Flip
Another augmentation technique is to flip the image.  We strongly recommend to do the horizontal flip only.  Vertical flip of human face always confuse the CNN models.

There are other techniques as well like rotation, scale, crop, gaussian noise, etc.  We did not apply those due to the result of only using flipping is encouraging enough.

## CONCLUSION
In this paper, we presented 2 different CNN models, Mini- Xception and Alexnet for facial emotion detection. In our experiment, we evaluated the models by 5-fold cross-validation and using new set of testing data retrieved from the web. The AlexNet model reached 69% test accuracy in our new testing data which is better than Mini-Xception which is 67.6%. On the other hand, for cross validation accuracy, AlexNet having 62.2% also better than Mini-Xception which is 58.8%. In general, emotion with strong facial expression such as Happy and Surprise are getting better performance.  

Future work might focus on trying out other types of CNN models, like VGGNet, Inception and ResNet or tuning more parameters and layers to construct an optimal model.
