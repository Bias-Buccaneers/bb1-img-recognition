# Bias Buccaneers Image Recognition Challenge

## Introduction

Welcome to the first bias bounty of [Bias Buccaneers](https://biasbounty.ai/). This competition will open October 20, 2022 and close on December 4, 2022. For our first challenge, we will inspect bias at the source: the data. We ask you to create a model that works on three common areas of image bias: skin tone, perceived gender, and age group.

In this challenge, we supply approximately 15,000 images of synthetically generated human faces. The primary challenge is to build a machine learning (ML) model that labels each image with its most likely skin tone, perceived gender, and age group. To get you started, we’ll supply labels for around 10,000 of these images.

This dataset is split into a training set of about 12,000 images and a test set of 3,000 images. You can choose to train your model using labeled images and their labels (supervised approach), only the images but not labels (unsupervised approach), or any mix of labeled and unlabeled images in the training set. The test set is solely for evaluating your model, and consists of only labeled images.

To make the task a tad more fun (and challenging!), not all images in our dataset are faces. About 20% of the images (we won’t tell you which ones!) are actually non-facial images randomly chosen from [ImageNet](https://www.image-net.org/).

## Prizes

The 3 models that score the highest according to our grading criteria below get prizes.

1st prize: $6,000 USD 

2nd prize: $4,000 USD

3rd prize: $2,000 USD

But wait, there’s more! For overachievers, there is a second $4,000 USD extra credit prize for the entrant who creates the **Best Unsupervised Model**.

Besides these, we'll announce fun competitions periodically, with swags and goodies up for grabs. Follow our Twitter handle [@BiasBounty](https://twitter.com/BiasBounty) to keep an eye out for those!

## Grading Criteria
When you’re ready to submit, you can run the submission code that sends us your code and results. Your score is based on:

* Accuracy of the tagging model for each demographic attribute
* Disparity in classification accuracy across different classes within each demographic attribute
* Randomness in tags given to the ‘noisy’ ImageNet samples 
* Efficiency of code, measured as how long it takes for the code to produce predictions

## Scoring Rubric

There are four aspects of scoring: Accuracy, Disparity, Randomness, and Efficiency. We start with the test set accuracy values of detecting skin tone (10 classes per the Monk Skin Tone Scale), perceived gender (2 classes: female and male), and age (4 classes: 0-17, 18-30, 31-60, 61-100). Our final score is a weighted sum of these accuracies, adjusted for the other three factors.

### Accuracy
An input sample is harder to classify if the possible number of classes is high. Based on this rationale, we assign multipliers to an accuracy value that is equal to number of classes for each of the three labels.

| Label | Skin tone | Age | Gender |
| --- | --- | --- | --- |
| Multiplier | 10x | 4x | 2x

### Disparity
For a given label (e.g. skin tone) classification model to show less disparity, but we want the range of accuracies for all possible classes of this model to be small. 
We measure this range using the difference of the maximum and minimum accuracies across all classes (Disp), penalizing more for a higher value of Disp. To account for the fact it is more difficult to maintain low disparity if number of possible classes is higher, we give different power multipliers for the accuracy values of three labels.

| Label | Skin tone | Age | Gender |
| --- | --- | --- | --- |
| Multiplier | 1 - Disp<sup>5</sup> | 1 - Disp<sup>2</sup> | 1 - Disp

Since we do not know which images in the train or test sets are from ImageNet, scores in the public leaderboard score will be based on only the above two factors.

$$ \text{Score}_1  = 10 \text{Acc}_s ( 1-\text{Disp}_s^5 ) + 4 \text{Acc}_a ( 1-\text{Disp}_a^2 ) + 2 \text{Acc}_g ( 1-\text{Disp}_g )$$

### Randomness
For each of the three labels, we take the distribution of predicted classes for the known ImageNet samples in our held-out validation set, and compare this with the uniform distribution with that many classes (e.g. compare with (0.25, 0.25, 0.25, 0.25) for age) using a [chi-squared test](https://en.wikipedia.org/wiki/Chi-squared_test). We give positive multipliers for each test that fails to reject (i.e. p-value less than 0.05), with higher multipliers for higher number of classes. Multipliers can be stacked with each other, i.e. you get multipliers for all the randomness tests your model passes.

| Label | Skin tone | Age | Gender |
| --- | --- | --- | --- |
| Multiplier | 1.3x | 1.2x | 1.1x

### Efficiency

Efficiency is evaluated by inference time on the validation set, according to our in-house compute setup. Your _Eficiency multiplier_ will be based on the percentile your best score belongs in when compared to best submissions from all participants.

| Percentile | Top 10% | 15%-25% | Rest |
| --- | --- | --- | --- |
| Multiplier | 1.2x | 1.1x | 1x

After the submission period finishes, we'll take your latest submitted model, obtain $\text{Score}_1$ on validation data, then use the above two multipliers to compute the final score for your submission.

$$ \text{Score}_2 = \text{Randomness multiplier} \times \text{Efficiency multiplier} \times \text{Score}_1 $$

Finally, higher values of both $\text{Score}_1$ and $\text{Score}_2$ are better.

## Submission
Each submission should be in the form of a GitHub repository, and consist of one set of model, code, and results on the test data. If your model is unsupervised, you can choose to enter the same model in the unsupervised model challenge. If not, you can submit a separate unsupervised model---with a second set of code and results---to the unsupervised model challenge. 

When the submission period starts (Nov 15), you can score a model you'd like to submit on the labeled test set of images and submit it to us by running the submission code provided in the Quickstart notebook. Multiple submissions are allowed. These scores (Score<sub>1</sub>) will go into our public leaderboard. After the submission period ends, we will test and score your final submission against a privately-held labeled holdout sample of images. Prizes will be awarded based on scores (Score<sub>2</sub>) in this private leaderboard. We'll release the private leaderboard after prizes are given out.

## How do I get started? 
To sign up, visit us at https://biasbounty.ai/8-bbb. Once you register as a crew, you'll be given access to the train and test datasets. The notebook in this reponsitory provides a starting point for working with this data.

Each entrant will have the opportunity to sign up for $5,000 USD of free AWS credit to complete the challenge. (Special thanks to our awesome partners at Amazon!) Once you enter, you will receive the password to access our challenge data. 

We will also be hosting periodic competitions throughout the month for fun items, like Kindles! If you are entering as a group, please let us know if you want to receive our Mutiny in a Box event bundle!

## What happens to my submission after the competition closes?

That’s entirely up to you. You retain full rights to your submission, including the choice of license, a public or private repository, and rights to its future use.  If it's private, we only ask you provide access to our [admin](https://github.com/shubhobm) during the duration of the challenge. If you’re interested in working with the Bias Buccaneers team to take the next steps with a winning submission, let’s talk!
