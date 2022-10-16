# Bias Buccaneers Image Recognition Challenge

## Introduction

Welcome to the first bias bounty of [Bias Buccaneers](https://biasbounty.ai/). This competition will open October 20, 2022 and close on December 4, 2022. For our first challenge, we will inspect bias at the source: the data. We ask you to create a model that works on three common areas of image bias: skin tone, perceived gender, and age group.

In this challenge, we supply approximately 15,000 images of synthetically generated human faces. The primary challenge is to build a machine learning (ML) model that labels each image with its most likely skin tone, perceived gender, and age group. To get you started, we’ll supply labels for around 10,000 of these images.

This dataset is split into a training set of about 12,000 images and a test set of 3,000 images. You can choose to train your model using labeled images and their labels (supervised approach), only the images but not labels (unsupervised approach), or any mix of labeled and unlabeled images in the training set. The test set is solely for evaluating your model, and consists of only labeled images.

To make the task a tad more fun (and challenging!), not all images in our dataset are faces. About 20% of the images (we won’t tell you which ones!) are actually non-facial images randomly chosen from [ImageNet](https://www.image-net.org/).

## Prizes

The 3 models that score the highest according to our grading criteria (see below) get prizes.
1st prize: USD 6,000 
2nd prize: USD 4,000
3rd prize: USD 2,000

But wait, there’s more! 

For overachievers, there is a second USD 4,000 extra credit prize for the entrant who creates the Best Unsupervised Model. 

## Grading Criteria
When you’re ready to submit, you can run the submission code that sends us your code and results. Your score is based on:

* Accuracy of the tagging model for each demographic set
* Disparity in classification accuracy across different subgroups within each demographic set
* Randomness in tags given to the ‘noisy’ ImageNet samples 
* Efficiency of code, measured as how long the code takes to run

## Submission and Scoring
Each submission should consist of one set of model, code, and results on the test data. If your model is unsupervised, you can choose to enter the same model in the unsupervised model challenge. If not, you can submit a separate unsupervised model---with a second set of code and results---to the unsupervised model challenge. 

Submissions will be evaluated based on a single score that takes into account the above factors. When the submission period starts (Nov 15), you can score your model on the labeled test set of images and submit it to us by running the submission code provided on our github repo. Multiple submissions are allowed. These scores will go into our public leaderboard. After the submission period ends, we will test and score your final submission against a privately-held labeled holdout sample of images. Prizes will be awarded based on scores in this private leaderboard.


## How do I get started? 
To sign up, visit us at https://biasbounty.ai/8-bbb. Once you register as a crew, you'll be given access to the train and test datasets. The notebook in this reponsitory provides a starting point for working with this data.

Each entrant will have the opportunity to sign up for USD 5,000 of free AWS credit to complete the challenge. (Special thanks to our awesome partners at Amazon!) Once you enter, you will receive the password to access our challenge data. 

We will also be hosting periodic competitions throughout the month for fun items, like Kindles! If you are entering as a group, please let us know if you want to receive our Mutiny in a Box event bundle!
