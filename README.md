# Damage Assessment of Tubbs Fire to Santa Rosa Residential Buildings
---
Authors: Saied Mighani, Anna Bukareva, Brendan Chan

<div style="text-align:center"><img src="plots/NASA-satellite-image-header.png" /></div>

####  [[Source for satellite image]](https://www.nasa.gov/image-feature/goddard/2018/nasa-satellite-shows-california-shrouded-in-smoke)
=======

### Problem Statement

The Tubbs Fire was a wildfire in Northern California during October 2017. At the time, the Tubbs Fire was the most destructive wildfire in California history, [https://en.wikipedia.org/wiki/Tubbs_Fire] burning parts of Napa, Sonoma, and Lake counties, inflicting its greatest losses in the city of Santa Rosa The damage was enormous. 

When a fire starts to spread, quick and accurate situational information is critical to an effective response. Before responders can act in the affected area, they need to know the location, cause and severity of damage. But disasters can strike anywhere, disrupting local communication and transportation infrastructure, making the process of assessing specific local damage difficult, dangerous, and slow. [https://www.challenge.gov/challenge/diu-xview2-assessing-building-damage/]

### Project Goal
---
Our goal is to help the Humanitarian Assistance & Disaster Recovery (HADR) automate the damage assessment by comparing pre-disaster and post-disaster of high resolution satellite images to accelerate recovery effects for natural disasters. Automated comparison using AI helps identify the affected area.

---
### The Process
---
The import, data process, as well as modeling and visualizatons were all performed in Python. In order to perform image analysis and processing for this project, convolutional neural network (CNN) models were used. They work phenomenally well on computer vision tasks like image classification, object detection, image recognition, etc.

The project directory is structured as follows:
```
project-global_warming_NLP
    
|__ assets/
|__ codes/
<<<<<<< HEAD
|  |__P02_Data_Cleaning_Imageview.ipynb
|  |__P03_modeling.ipynb
|__ datasets/
|  |__train/
|  |__test/ 
|     |__images/
|     |__labels/
|     |__targets/
=======
|  |__ P01_API_requests.ipynb  
|__ datasets/
>>>>>>> origin
|__ plots/
|__ Executive_slides_satellie_CNN.pdf
|__ README.md
```

- Using data gathered by SpaceNet satellite images and pre-trained baseline localization and classification models, pre/post images are inputted, our model assesses the building damage by using various computer vision techniques, and lastly predicts output PNG images for damage.
- Input images are square RGB image files in PNG format, with height and width of 1024 pixels. Pre/post pairs are identified by matching numerical IDs for each set of pre/post filenames.
- Image Detection, Localization, and Classification: The localization model properly identifies and locates buildings within the image. This model is based on a SpaceNet2 submission by Motoki Kimura, which features an altered U-Net architecture. The baseline classification model classifies the damage of the buildings before and after the Tubbs fire and is a pre-trained ResNet50 on ImageNet. The model has a precision score of 0.87 for no damage and 0.5 for destroyed classification.
- Labels and Annotations: Polygons were annotated and damage scores were labeled on the training set for each building by these baseline models.
- Image Segmentation: A pixelated mask for each object was outputted providing an exact outline of the objects within the image from json files. The main target for our image segmentation was the building bodies.

---
### Results
---
Model Training and Results: We split the labeled (destroyed versus no-damage) houses into train/validation and test datasets. Then, selected a pre-trained CNN model and trained it further using our train/validation dataset. Eventually, we predicted the target lables for the test dataset (see Figure below)
[Figure for predictions]

As figure shows, all the labeles were correctly predicted. Hence, the mode accuracy was 1. Although, it seems like a perfect model, there is one drawback in our variance assessment. Our test dataset was selected from the same image set as train, so we might have had some leakage from training to test. As a future attempt, we will test the model on a completely new dataset for a better assessment of model overfit behavior.

---
### Next Steps and Further Improvements
---
If we had more time to work on this project, one significant improvement we can make to the model is to add some granularity to the classification. The current classifier only classifies buildings as either having no damage or being completely destroyed. Obviously, there are cases in between where the buildings are only partially damaged. Given more time, we would add additionally classifications to indicate the level of damage e.g. a number classification system where 0 is undamaged and 5 is completely destroyed. All the numbers in between would simply specify the level of damage. 

Another thing we could work on is to gather more data and train our own neural networks for both object detection and classification. This wouldn't necessarily improve the efficacy of the code, but it would give us a greater insight into the inner workings of convolutional neural networks.

Additionally, we could extend the model to other natural disasters, which may or may not require us to train our own CNN model. The model works remarkably well so far on buildings damaged by fires. I would imagine that we could also extend it to damage caused by floods or earthquakes. Perhaps even train a classifier that can distinguish the different types of damage. 

Finally, a convenient thing to have would be a code that takes in housing data in order to predict the cost of the damages. 
