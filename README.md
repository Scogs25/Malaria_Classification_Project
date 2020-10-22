# Malaria_Classification_Project
By Michael Scognamiglio and Amir Edris 
## Table of Contents
1. Project Overview
1. Business Case 
1. Repo Structure and Project Approach
1. Modeling 
1. Final Modeling and Analysis
1. Visualizing Classifications
1. Conclusions 
1. Next Steps
## Project Overview
Malaria is silently a large killer to this day. In fact, every year there are over 200 million cases with about 400,000 deaths.
Malaria is caused due to parasites transmitted through mosquito bites. Thus, Parasite counts are used to diagnose malaria  correctly. However, the manual counting of parasites varies depending on the skill and expertise of the microscopist. Depending on the conditions and treament of these scientisits, accurate diagnosis can vary. Thus, the goal of this project is to create a highly accurate image classification model that can quickly and effictively diagnose Malaria.The model will be trained on a kaggle dataset of approximatly 28,000 photos of infected and uninfected cells. The original dataset cvan be found on Kaggle at the following link: https://www.kaggle.com/iarunava/cell-images-for-detecting-malaria
## Business Case 
The Business Case for this project is for any labroratory or organization that has an interest in improving Malaria Diagnosis. Our model will provide many advantages to the currently used manual counting methods. Our model will provide a more reliable and standardized approach to diagnosing Malaria. It will reduce the workload of malaria field workers, thus allowing more patients to be taken care of. It will also reduce the costs related to diagnosis. 
## Repo Structure and Project Approach
 All visulaizations used for both this Readme and the presenation pdf can be found in the pngs folder.
 The pdf '" contains the  pdf presentation of this project.
 
Please see the goals of the code contained in the master notebook below. 
 ### Master_notebook.ipynb
    - Import all necessary libraries and modules to use and manipulate image data as well as build  models
    - For ease of use, multiple functions are declared at the top of the notebook
    - Look at Regular and Infected Cells to look for visual differences
    - Look at dataset's class distribtuions and use to build a dummy classifier model
    - Prepare both complicated and simple CNN models to see how well they perform classfications, try different hyperparamters to optimize performance.
    - Compare Models' performances on evaluation metrics and select the best performing model
    - Select Final model and test for overfitting, correct for overfitting accordingly
    - Look at final model's misclassifications and analyze those
    - Present Conclusions,recommendations, next steps
