# CT5146 Assignment 2

This task is focused on sentiment classification and span extraction from tweets. Please complete this task and upload your answers to Canvas as an iPython Notebook or a PDF. This assignment is due by 23:59 on December 10th 2023. Late submissions will be penalised by 1% for each day after this date. This is an individual assignment and your work must be your own.

You may use libraries such as SciKit-Learn to complete this assignment, however you should justify the choice of functions from these libraries.

**Summary**

In this task, given a tweet (text) we have two objectives:

1. Sentiment classification: Classify the tweet into one of three classes (positive, negative, neutral).

2. Sentiment span extraction: Extract the sequence of words from the tweet that expresses the given sentiment.

Consider the following example from the train dataset:

| textID | text | selected_text | sentiment |
| ------ | ---- | ------------- | --------- |
| 266b8792a0 |Just broke my favorite necklace  superglue? | Just broke my favorite necklace | negative |
| 8f3e73cf09 | "Screw the reviews, I thought Wolverine was awesome. But not enough Dominic Monaghan for my liking." | I thought Wolverine was awesome. | positive |
|... | ... | ... | ... |
| 266b8792a0 |Just broke my favorite necklace  superglue? | Just broke my favorite necklace | negative |


The dataset is divided into `train`, `dev` and `test` sets. The `train` set is used for the model training, while the `dev` set is used for validation and hyperparameter tuning.

The test dataset has **no sentiment labels**. This dataset split will be used for **leaderboard submission** for sentiment classification modelling, described in section 2.

# 1. Data Analysis
    
## Task 1a

Plot a group bar plot to show the distribution of sentiment classes (positive, negative, neutral) in the train and dev dataset. As shown in the following illustration. `(10 marks)`
    
    
   <img src="https://github.com/gauneg/gauneg.github.io/blob/main/ds1.jpg?raw=true" alt="PLOT EXAMPLE" width="400px"/>
# 2. Sentiment Classification

## Task 2a

Train a sequence classification model. The model should take the `text` as input and return one out of 3 sentiment classes: `negative`, `neutral` or `positive`.



<img src="https://github.com/gauneg/gauneg.github.io/blob/main/sentiment_classification.png?raw=true" alt="PLOT EXAMPLE" width="500px"/>

    
INPUT : (`text`)

OUTPUT: `sentiment_class` i.e. one class from `(positive, negative, neutral)`


* You should preprocess the data in the training and development sets and extract feature vectors using either bag-of-words or TF-IDF. `(15 marks)`
* Using these features please train a classifier using a method such Support Vector Machines (SVM) `(10 marks)`

Please provide an  implementation along with an **explanation** (no more than 5 0 words) of the method used and any libraries you used to do this.

## Task 2b

Use the `text` and `sentiment` of the dev set to calulate the efficiency of your model by calculating the following metrics for each class:
    
- Precision

- Recall

- F1 Score
    
Considering it is a multi-class classification task, you should also report the macro-average scores in your implementation of the automatic metrics.
Please provide an implementation along with an **explanation** (no more than 50 words) of the method used. `(5 marks)`


## Task 2c

Based on the methods discussed in the lecture suggest **ONE** improvement or alternative approach that can be applied to the sentiment classification task as in Task 2a. This may be through better feature extraction, new modelling or through an alternaitve methodology.

You should implement this approach and compare the results using the evaluation from Task 2b.

Provide an **explanation** of your approach in no more than 100 words.

`(20 marks)`

## Task 2d
Join the closed kaggle competition at this [link](https://www.kaggle.com/t/c485f589d0694836be2dcecd01a7da4a). Follow the instructions. In order to join the competion login to kaggle using your `universityofgalway` email account. Make a successful submission. Apply the system you developed in Task 2c to the test dataset and submit this result. Marks will be awarded based on the quality of the result.

`(10 marks)`

Format of the test set:


| textID | text | selected_text |
| ------ | ---- | ------------- |
| 266b8792a0 |Just broke my favorite necklace  superglue? | Just broke my favorite necklace |
| 8f3e73cf09 | "Screw the reviews, I thought Wolverine was awesome. But not enough Dominic Monaghan for my liking." | I thought Wolverine was awesome. |
|... | ... | ... |
| 266b8792a0 |Just broke my favorite necklace  superglue? | Just broke my favorite necklace |

Format of the submission file `(.csv format)`:


| textID | sentiment |
| ------ | --------- |
| 266b8792a0 | negative |
| 8f3e73cf09 | positive |
|... | ... |
| 266b8792a0 | negative |

# 3. Span Extraction
## Task 3a


Our goal for this task is to extract the sentiment span, given the text and the given sentiment (true sentiment label) as input. The sentiment span is a subsection of the text that expresses the sentiment that classifies the text overall.

INPUT : (`text`, `sentiment`)

OUTPUT: `selected_text`

<img src="https://github.com/gauneg/gauneg.github.io/blob/main/assignment_diag.png?raw=true" alt="PLOT EXAMPLE" width="500px"/>


1. Describe in no more than 200 words a system that could be used to identify the sentiment span. You should consider the methodology potentially including how features are extracted, what models could be used and what procedures should be used to train the model. `(10 marks)`

2. Implement this system and apply it to the train and development splits of the dataset. `(15 marks)`

## Task 3b

1. Describe an automatic metric that can be used to evaluate the task of span extraction. Implement this metric and use it to evaluate the performance of the system you developed in Task 3a. `(5 marks)`
