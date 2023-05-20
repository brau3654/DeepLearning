# Deep Learning Final

## Overview

This project was the final for my Deep Learning class. We were given the titanic dataset from Kaggle and particippated in the cometition. The chalenge was to see how good a model you can create to predict which passengers lived and died. We did this using feed forward neural networks and the file in this repo is straight from Google Collab. 

---

## Data Cleaning
The data we were given had 10 features to use. Survival was a binary variable of whether the person survived. Pclass was the class the individual was staying in. The options are 1st, 2nd, and 3rd. Sex is just the sex of the person. Age is their age. Sibsp is the number of siblings and spouses that person had with them on the Titanic. Parch is the number of parents and children the person had with them. Ticket is the persons ticket number if it is known. Fare was the amount that was paid for the ticket. Cabin is the person’s cabin number. Embarked is what port the person got on the Titanic at.
Cabin, since there were so many missing values, I turned into a categorical variable of whether we knew the cabin the person was staying in. My logic was that maybe there wasn’t an official record of it and the cabins we knew were from people who survived telling us their cabin number. The ticket feature on its own I dropped since there seemed little logic to it, but I did try to extract features from it. I created categories for whether it was A5, PC, CA, SCT, FCT, LINE based on the presence of the letters in the ticket id. I had no idea if any of these had actual meaning, but I figured it couldn’t hurt to try them in a model. 

---

## Models of Note
The most interesting model created was my “Codify All” model. It used every feature available. 3This model would get training accuracies up to 89% but there was overfitting with test accuracy being 75% and submission not being much better. One thing I tried with this model that helped get better numbers was using a learning rate scheduler. With this the learning rate would slowly decrease as the model went through epochs theoretically catching smaller trends in the data. Batch normalization also increased the training accuracy by 8% the first time I used it but it left testing accuracy behind and the submission was no better. The best model I created used only gender and class to predict survival. I experimented with model size, going up to a starting layer of 640 nodes but nothing did better than the 32, 16, 8, 1 node model. By decreasing learning rate and increasing epoch count I thought I could scrape a bit more accuracy out but it had little effect at best and at worst made the submission accuracy worse.
