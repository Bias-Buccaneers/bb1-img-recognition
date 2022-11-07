# Bias Buccaneers Image Recognition Challenge: Datasheet

<a id="top"></a>

## Contents

[Motivation](#motivation)

[Composition](#composition)

[Collection Process](#collection-process)

[Preprocessing](#preproc)

[Uses](#uses)

[Distribution](#distribution)

[Maintenance](#maintenance)

## Motivation

### For what purpose was the dataset created?
#### Was there a specific task in mind? Was there a specific gap that needed to be filled? Please provide a description.


This dataset is for use in the [algorithmic bias bounty](https://biasbounty.ai/8-bbb) hosted by  [Bias Buccaneers](https://biasbounty.ai/). The purpose of the challenge is to create a model that works on three common areas of image bias in classifying images of human faces: the recognition of skin tone, perceived gender, and age group. This dataset is split into a training set of about 12,000 images and a test set of 3,000 images. Participants can choose to train a model from scratch or fine-tune a previously trained model using labeled images and their labels (supervised approach), only the images but not labels (unsupervised approach), or any mix of labeled and unlabeled images in the training set. The test set is solely for evaluating a submitted model, and consists of only labeled images.

Not all images in our dataset are faces. About 20% of the images are actually non-facial images randomly chosen from ImageNet. The purpose of these images is to add ‘noise’ to test the model quality.

### Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)?

The dataset is composed of open-sourced images from [Unsplash](www.unsplash.com).

The annotations were created by Bias Buccaneers.

Annotations were randomly assigned to the ImageNet samples for each class (perceived gender, skin tone, age), with equal weights to all labels of a class.

### Who funded the creation of the dataset?
#### If there is an associated grant, please provide the name of the grantor and the grant name and number.

The creation of the dataset annotations was funded by Bias Buccaneers.

### Any other comments?
This dataset is drawn from multiple sources, including synthetic data, human face images from Unsplash.com and cropped by Bias Buccaneers, and ‘noise’ data from Image Net. This dataset was later tagged by Bias Buccaneers. 

Unless otherwise specified, by ‘dataset’ we refer to the data used for the Bias Bounty competition. We specify the sampling and labeling mechanism of the ImageNet samples at respective places, and direct the reader to the ImageNet website for more information. Similarly, many of the legal and ethical use requirements are assumed in good faith from material on www.unsplash.com

[back to top](#top)

## Composition

Most of these questions are intended to provide dataset consumers with the information they need to make informed decisions about using the dataset for specific tasks. The answers to some of these questions reveal information about compliance with the EU’s General Data Protection Regulation (GDPR) or comparable regulations in other jurisdictions.

### What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)?

The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).
 
### Are there multiple types of instances (e.g., movies, users, and ratings; people and interactions between them; nodes and edges)? Please provide a description.

The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).

### How many instances are there in total (of each type, if appropriate)?

The dataset contains a total of 12,283 images of human faces. The ImageNet sample data consists of 3,000 randomly selected images from ImageNet.

### Does the dataset contain all possible instances or is it a sample (not necessarily random) of instances from a larger set?

The dataset contains a randomized sample of images of human faces. The dataset is a subset of a larger set of open-sourced images from [Unsplash](www.unsplash.com).

### If the dataset is a sample, then what is the larger set? Is the sample representative of the larger set (e.g., geographic coverage)? If so, please describe how this representativeness was validated/verified. If it is not representative of the larger set, please describe why not (e.g., to cover a more diverse range of instances, because instances were withheld or unavailable).

The dataset contains a randomized sample of images of human faces. The dataset is a subset of a larger set of open-sourced images from [Unsplash](www.unsplash.com).

The ImageNet samples are obtained as random samples from the larger ImageNet dataset. We used the [ImageNet Downloader](https://github.com/mf1024/ImageNet-Datasets-Downloader) tool to randomly sample 100 random images each, for 30 randomly selected labels.

### What data does each instance consist of?
“Raw” data (e.g., unprocessed text or images) or features? In either case, please provide a description.

Each instance contains an image processed by [Unsplash](www.unsplash.com), and further cropped by Bias Buccaneers. 

### Is there a label or target associated with each instance? If so, please provide a description.

Each instance has been annotated for approximate gender, age range, and skin tone following generalized best practices (Eg. We chose to avoid "race" and instead used "skin tone" following the [Monk Skin Tone scale](https://blog.google/products/search/monk-skin-tone-scale/)).

Over the course of two weeks, 10 human annotators completed tagging on the data set, with transparent instructions across each annotation type (including examples of Monk skin tone scale). 100% of the dataset was further reviewed by a second annotator. To further reduce potential errors, images that produced conflicting annotations by reviewers were set aside. As a third and final step, the Technical Program Manager in charge of the auditing process by reviewing a 2.5% random sample of labels to ensure quality of final annotations.

### Is any information missing from individual instances? If so, please provide a description, explaining why this information is missing (e.g., because it was unavailable). This does not include intentionally removed information, but might include, e.g., redacted text.

To the best of our knowledge, no. Information was limited to what was provided via open-source license from [Unsplash](www.unsplash.com).

### Are relationships between individual instances made explicit (e.g., users’ movie ratings, social network links)? If so, please describe how these relationships are made explicit.

To the best of our knowledge, no. 
Information was limited to what was provided via open-source license from [Unsplash](www.unsplash.com).

### Are there recommended data splits (e.g., training, development/validation, testing)? If so, please provide a description of these splits, explaining the rationale behind them.

This dataset contains a total of 15,283 images, is split into a training and test set of 12,283 and 3,000 images, respectively. Among the training set of images, 6,053 are labeled images of faces, 3,730 are unlabeled images of faces, and 2,500 are randomly labeled images of ImageNet samples. Among the test set of images, 2,500 are labeled images of faces and 500 are labeled  images of ImageNet samples.

### Are there any errors, sources of noise, or redundancies in the dataset? If so, please provide a description.

The annotations may include various biases; the purpose of the "bias bounty" is to advance research on dataset and model bias, by design.

### Is the dataset self-contained, or does it link to or otherwise rely on external resources (e.g., websites, tweets, other datasets)?

The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).

### If it links to or relies on external resources, a) are there guarantees that they will exist, and remain constant, over time; b) are there official archival versions of the complete dataset (i.e., including the external resources as they existed at the time the dataset was created); c) are there any restrictions (e.g., licenses, fees) associated with any of the external resources that might apply to a future user? Please provide descriptions of all external resources and any restrictions associated with them, as well as links or other access points, as appropriate.

The dataset is limited to images of human faces that have been verified as open-source by www.unsplash.com. (a) there are no future guarantees that this dataset will exist on unsplash in the future (b) there are no official archival versions, except what is on unsplash, and (c) there are no licenses, fees and restrictions based on the unsplash TOS

We do not intend to distribute this dataset widely for purposes beyond the bias bounty program. 

### Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor-patient confidentiality, data that includes the content of individuals’ non-public communications)? If so, please provide a description.

No, per [Unsplash](www.unsplash.com).

### Does the dataset contain data that, if viewed directly, might be offensive, insulting, threatening, or might otherwise cause anxiety? If so, please describe why.

No

### Does the dataset relate to people? If not, you may skip the remaining questions in this section.

Yes, the dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).

### Does the dataset identify any subpopulations (e.g., by age, gender)? If so, please describe how these subpopulations are identified and provide a description of their respective distributions within the dataset.

The sampling strategy was probabilistic following the standard query algorithm of www.unsplash.com across all ages, genders, and skin tones.

### Is it possible to identify individuals (i.e., one or more natural persons), either directly or indirectly (i.e., in combination with other data) from the dataset? If so, please describe how.

Yes; The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).

### Does the dataset contain data that might be considered sensitive in any way (e.g., data that reveals racial or ethnic origins, sexual orientations, religious beliefs, political opinions or union memberships, or locations; financial or health data; biometric or genetic data; forms of government identification, such as social security numbers; criminal history)? If so, please provide a description.

Each image has been annotated for approximate sex, age range, and skin tone following generalized best practices (Eg. We chose to avoid “race” and instead used “skin tone” following the Monk Skin Tone scale.

### Any other comments?

N/A

[back to top](#top)

## Collection process

The answers to questions here may provide information that allow others to reconstruct the dataset without access to it.

### How was the data associated with each instance acquired?
Each image has been annotated for approximate sex, age range, and skin tone following generalized best practices (Eg. We chose to avoid "race" and instead used "skin tone" following the Monk Skin Tone scale.

Each annotation was completed by a human team of trained image annotators, following best practices for initial annotation, confirmation, and follow on quality assurance. 

### Was the data directly observable (e.g., raw text, movie ratings), reported by subjects (e.g., survey responses), or indirectly inferred/derived from other data (e.g., part-of-speech tags, model-based guesses for age or language)? If data was reported by subjects or indirectly inferred/derived from other data, was the data validated/verified? If so, please describe how.

The annotations were indirectly inferred; the annotations were not validated or verified by the subjects. We use the term ‘perceived’ to reflect this limitation.

### What mechanisms or procedures were used to collect the data (e.g., hardware apparatus or sensor, manual human curation, software program, software API)? How were these mechanisms or procedures validated?

The dataset contains a randomized sample of images of human faces. The dataset is a subset of a larger set of open-sourced images from [Unsplash](www.unsplash.com). Standard internet download as used to collect the images from the public website.

### If the dataset is a sample from a larger set, what was the sampling strategy (e.g., deterministic, probabilistic with specific sampling probabilities)?

The dataset was downloaded to have a balanced dataset across all subgroups for each of our 3 demographic features. 

### Who was involved in the data collection process (e.g., students, crowdworkers, contractors) and how were they compensated (e.g., how much were crowdworkers paid)?

Bias Buccaneers team members were involved in the data collection process on a volunteer (unpaid) basis. The source data collection terms are outlined at 

### Over what timeframe was the data collected?

Data waere collected during the month of October 2022.

### Does this timeframe match the creation timeframe of the data associated with the instances (e.g. recent crawl of old news articles)? If not, please describe the timeframe in which the data associated with the instances was created.

Information was limited to what was provided via open-source license from [Unsplash](www.unsplash.com) which does not include any information on the original image creation date.

### Were any ethical review processes conducted (e.g., by an institutional review board)? If so, please provide a description of these review processes, including the outcomes, as well as a link or other access point to any supporting documentation.

There is no IRB process for this form of data. Please review unsplash privacy policy here: https://unsplash.com/privacy.

### Does the dataset relate to people? If not, you may skip the remainder of the questions in this section.

Yes; The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).

### Did you collect the data from the individuals in question directly, or obtain it via third parties or other sources (e.g., websites)?

The dataset was built from the open-source website [Unsplash](www.unsplash.com).

### Were the individuals in question notified about the data collection?

No; The dataset is limited to images of human faces that have been verified as open-source by https://unsplash.com/license.


### If so, please describe (or show with screenshots or other information) how notice was provided, and provide a link or other access point to, or otherwise reproduce, the exact language of the notification itself.

N/A

### Did the individuals in question consent to the collection and use of their data? If so, please describe (or show with screenshots or other information) how consent was requested and provided, and provide a link or other access point to, or otherwise reproduce, the exact language to which the individuals consented.

Please see the Unsplash license: https://unsplash.com/license.

### If consent was obtained, were the consenting individuals provided with a mechanism to revoke their consent in the future or for certain uses? If so, please provide a description, as well as a link or other access point to the mechanism (if appropriate).

Please see https://unsplash.com/privacy#rights-regarding-your-personal-information.

### Has an analysis of the potential impact of the dataset and its use on data subjects (e.g., a data protection impact analysis) been conducted? If so, please provide a description of this analysis, including the outcomes, as well as a link or other access point to any supporting documentation.

There has not been a formal analysis of impact of use on data subjects. However, Bias Buccaneers and the Bias Buccaneers are limiting access to the data set for challenge purposes only. This data will not be available widely for other purposes.

### Any other comments?

N/A

[back to top](#top)

## <a id="preproc"></a> Preprocessing/cleaning/labeling
The questions in this section are intended to provide dataset consumers with the information they need to determine whether the “raw” data has been processed in ways that are compatible with their chosen tasks. For example, text that has been converted into a “bag-of-words” is not suitable for tasks involving word order.

### Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)?

Each instance contains an image processed by [Unsplash](www.unsplash.com), and further cropped and annotated by Bias Buccaneers. 

### If so, please provide a description. If not, you may skip the remainder of the questions in this section.

Bias Buccaneers used an internal tool to auto-crop the images.

### Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? If so, please provide a link or other access point to the “raw” data.

The raw data remains on [Unsplash](www.unsplash.com).

### Is the software used to preprocess/clean/label the instances available? If so, please provide a link or other access point.

No. 

### Any other comments?

N/A 

[back to top](#top)

## Uses
These questions are intended to encourage dataset creators to reflect on the tasks for which the dataset should and should not be used. By explicitly highlighting these tasks, dataset creators can help dataset consumers to make informed decisions, thereby avoiding potential risks or harms.

## Has the dataset been used for any tasks already? If so, please provide a description.

The dataset was created for the Bias Bounty competition. There are no prior purposes. 

### Is there a repository that links to any or all papers or systems that use the dataset? If so, please provide a link or other access point.

N/A

### What (other) tasks could the dataset be used for?

The dataset could be used for many purposes, beneficial or malicious. Datasets on faces can be used to identify diseases, stop human trafficking or identify CSAM. Similarly datasets could be used to enable the surveillance state by improving image detection models for police or military use, or for commercial benefit. 

## Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses?

Since we cannot control the multiple possibilities of usage for this dataset, we choose to limit use. After the challenge is complete, the dataset will no longer be public. 

### For example, is there anything that a future user might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other undesirable harms (e.g., financial harms, legal risks) If so, please provide a description. Is there anything a future user could do to mitigate these undesirable harms?

N/A

### Are there tasks for which the dataset should not be used? If so, please provide a description.

Yes, the creators of this dataset do not want this dataset to be used to identify individuals for the purposes of public surveillance.  


### Any other comments?

N/A

[back to top](#top)

## Distribution

### Will the dataset be distributed to third parties outside of the entity (e.g., company, institution, organization) on behalf of which the dataset was created?
#### If so, please provide a description.

The dataset will be distributed to participants in our first bounty during the course of this challenge (Oct 20-Nov 30, 2022). After this date access will be closed.

### How will the dataset will be distributed (e.g., tarball on website, API, GitHub)?

The dataset will be distributed as a zipped file to participants in our first bounty. To get access to the dataset, participants need to

1. Officially register as a participant in the bounty with a working e-mail address
2. Request access to the dataset from using a link provided in the event portal that they get access to after registration
3. Agree to abide by our [Code of Conduct](https://biasbounty.ai/the-code) during the course of challenge.


### Does the dataset have a digital object identifier (DOI)?

No

### When will the dataset be distributed?
The dataset is available for distribution during the course of our first bounty (Oct 20-Nov 30), only to registered participants who request access.

Access will be provided only during the course of the challenge, and removed after Nov 30, 2022, 11:59 PM PDT.

### Will the dataset be distributed under a copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?

The dataset can only be used for the bounty. 

### If so, please describe this license and/or ToU, and provide a link or other access point to, or otherwise reproduce, any relevant licensing terms or ToU, as well as any fees associated with these restrictions.

N/A

### Have any third parties imposed IP-based or other restrictions on the data associated with the instances? If so, please describe these restrictions, and provide a link or other access point to, or otherwise reproduce, any relevant licensing terms, as well as any fees associated with these restrictions.

No; The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).


### Do any export controls or other regulatory restrictions apply to the dataset or to individual instances? If so, please describe these restrictions, and provide a link or other access point to, or otherwise reproduce, any supporting documentation.


No; The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com).

### Any other comments?

N/A

## Maintenance
These questions are intended to encourage dataset creators to plan for dataset maintenance and communicate this plan with dataset consumers.

### Who is supporting/hosting/maintaining the dataset?

[Bias Buccaneers](www.biasbounty.ai) is hosting the dataset.

### How can the owner/curator/manager of the dataset be contacted (e.g., email address)?

Please e-mail us at: info@biasbounty.ai

### Is there an erratum?
If so, please provide a link or other access point.

### Will the dataset be updated (e.g., to correct labeling errors, add new instances, delete instances)?
#### If so, please describe how often, by whom, and how updates will be communicated to users (e.g., mailing list, GitHub)?

The dataset was created for the Bias Bounty competition taking place during the month of November 2022. There is no intention to update this dataset at this time.

### If the dataset relates to people, are there applicable limits on the retention of the data associated with the instances (e.g., were individuals in question told that their data would be retained for a fixed period of time and then deleted)?
#### If so, please describe these limits and explain how they will be enforced.

The dataset is limited to images of human faces that have been verified as open-source by [Unsplash](www.unsplash.com). Unsplash abides by GDPR.

### Will older versions of the dataset continue to be supported/hosted/maintained?
#### If so, please describe how. If not, please describe how its obsolescence will be communicated to users.

N/A

### If others want to extend/augment/build on/contribute to the dataset, is there a mechanism for them to do so? If so, please provide a description. Will these contributions be validated/verified? If so, please describe how. If not, why not? Is there a process for communicating/distributing these contributions to other users? If so, please provide a description.

No, as this data will not be available for public use beyond the bias bounty. 

### Any other comments?

N/A

[back to top](#top)
