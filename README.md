# Malaria_Classification_Project
By Michael Scognamiglio and Amir Edris 
## Table of Contents
1. Project Overview
1. Business Case 
1. Repo Structure and Project Approach
1. Modeling 
1. Final Modeling and Analysis
1. Visualizing Classifications
1. Conclusions/ Next Steps
## Project Overview
Malaria is silently a large killer to this day. In fact, every year there are over 200 million cases with about 400,000 deaths.
Malaria is caused due to parasites transmitted through mosquito bites. Thus, Parasite counts are used to diagnose malaria  correctly. However, the manual counting of parasites varies depending on the skill and expertise of the microscopist. Depending on the conditions and treament of these scientisits, accurate diagnosis can vary. Thus, the goal of this project is to create a highly accurate image classification model that can quickly and effictively diagnose Malaria.The model will be trained on a kaggle dataset of approximatly 28,000 photos of infected and uninfected cells. The original dataset cvan be found on Kaggle at the following link: https://www.kaggle.com/iarunava/cell-images-for-detecting-malaria
## Business Case 
The Business Case for this project is for any labroratory or organization that has an interest in improving Malaria Diagnosis. Our model will provide many advantages to the currently used manual counting methods. Our model will provide a more reliable and standardized approach to diagnosing Malaria. It will reduce the workload of malaria field workers, thus allowing more patients to be taken care of. It will also reduce the costs related to diagnosis. The primary evaulation metric we used to compare models was accuracy. We chose accuracy becuase there was no class imbalance in our data so it provides us with the best metric to measure how well we are classifying the observations into their actual classes. Recall was the metric that was looked at second closest because it allows us to minimize false negatives (diagnosis is no malaria when the patient has malaria) which for our project is the worst case scenario.
![Image](https://github.com/Scogs25/Malaria_Classification_Project/blob/main/pngs/Class_Distributions.png)

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
 
## Modeling 
For Modeling, We believed that testing four types of models and consistently altering hyper parameters would best allow us to find the ideal model. We first created a dummy model that would predict the dominant class. However, as you can see above there was no numerically dominant class. Thus, We chose the infected class as the dominant to minimize false negatives. This model achieved an accuracy of exactly 50%. We also decided to create a simpler CNN model with less convultional and dense layers. This model achieved an accuracy of 93% on the validation set. We then decided to create a more complex CNN model to see how well it would perform. The complex CNN model achieved an accuracy of about 95% on the validation set. We then decided to use Transfer Learning to determine whether that could further improve performance. We used Google's prebuilt Model InceptionV3 which is trained on large amounts of medical data.  We acheived an accuracy of 92% on the validation set for that model.

## Final Modeling and Analysis 
Due to it outperforming all other models, We selected the Complex CNN model as our final model. Achieving 95% Accuracy on both our test sets and validation sets was certainly impressive. Also, this model achieved a recall of .96 on the infected class, We were very satisified with this result because it proved that we are effectively limiting our false negatives as well.

![Image](https://github.com/Scogs25/Malaria_Classification_Project/blob/main/pngs/Final_model_Accuraccy_curve.png)
![Image](https://github.com/Scogs25/Malaria_Classification_Project/blob/main/pngs/Final_model_Confusion_Matrix.png)

As can be seen above, this model accuractly classifies whether or not a cell is infected and it also minimizes incorrect classifications. Thus, we can feel confident this model can be highly effective as a diagnosis tool.

## Visualizing Classifications 

## Conclusions/Next Steps 
![Image](https://github.com/Scogs25/Malaria_Classification_Project/blob/main/pngs/Modeling_Accuracy_Comparisons.png)

Through this project, we generated a few insights that we felt were worth sharing.

1. In the case of misclassifications, we found that non parasite impurities were often misrecognized as parasites thus causing the misclassification. Thus, we would recommend screening through that data as much as possible before training your model. If possible, try to minimize the ambuiguity of cells. In other words, try to avoid cells with imopurites resembling parasites. 
1. We found two hyperparameters that were the most effective in boosting model performance. Those two parameters were the complexity of the CNN Model and the order of convolutional layers. We would thus recommend to begin with a simpler CNN but iteratively build it's complexity until you are satisfied with the model. We would also recommend testing different orders for the convultional layers to find which best works for your models. 
1. One area we would like to experiment with in the future is images containing mutiple cells. In terms of data collection, this method would be much quicker. It would also provide the model with more information. In the case of a CNN model, this is likely to result in the model finding more patterns it can use to help its classification abilites. Thus, we believe this type of model could boost performance even further
