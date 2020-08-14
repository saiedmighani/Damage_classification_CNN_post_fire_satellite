# Damage Assessment of Tubbs Fire to Santa Rosa Residential Buildings
#### CNN-based predictions from Sentinel(?) Satellite Images

<div style="text-align:center"><img src="plots/NASA-satellite-image-header.png" /></div>

#### Carr fire (July 23rd-30th) in Santa Rosa, CA [[Source for satellite image]](https://www.nasa.gov/image-feature/goddard/2018/nasa-satellite-shows-california-shrouded-in-smoke)
=======

Carr Fire between July23rd-30th in Santa Rosa, CA [[Source for image]](https://www.nasa.gov/image-feature/goddard/2018/nasa-satellite-shows-california-shrouded-in-smoke)
>>>>>>> origin


<br>

- ### Project Goal

The Tubbs Fire was a wildfire in Northern California during October 2017. At the time, the Tubbs Fire was the most destructive wildfire in California history, [https://en.wikipedia.org/wiki/Tubbs_Fire] burning parts of Napa, Sonoma, and Lake counties, inflicting its greatest losses in the city of Santa Rosa The damage was enormous. 

When a fire starts to spread, quick and accurate situational information is critical to an effective response. Before responders can act in the affected area, they need to know the location, cause and severity of damage. But disasters can strike anywhere, disrupting local communication and transportation infrastructure, making the process of assessing specific local damage difficult, dangerous, and slow. [https://www.challenge.gov/challenge/diu-xview2-assessing-building-damage/]

Therefore, our goal is to create a predictive model that automates the damage assessment of high resolution satelite images to accelerate recovery from natural disasters.

<br>

- ### Problem statement
---
Can we train a model that will look at the differnetial (pre/post) satellite image and discern the damage extent?

---

### <span style="color: green">Project structure
    
The import, data process, as well as modeling and visualizatons were all performed in python. The project directory is structured as follows:
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

The project was first run on a small dataset of only one satellite image pairs, then was extended to 30 images.

---

  
    
### <span style="color: green">Step 1 - Data collection
    

---    
    
### <span style="color: green">Step 2 - Data cleaning
---
### <span style="color: green"> Step 3 - EDA
--- 
    
### <span style="color: green">Step 4 - Modeling process
---
### <span style="color: green">Model Discussion
---    


### <span style="color: green">Step 5 - Evaluation and Conceptual Understanding
    
---
### <span style="color: green">Final recommendation points
