## Modeling customer retention using claim details and survey responses

Customer attrition, or the loss of customers, is used as a key performance indicator across several industries, including insurance. The insurance industry’s customer acquisition costs are high, so it is important to retain existing customers rather than only focus on getting new ones [1]. The distribution of resources for both customer retention and acquisition can be improved by being able to predict the likelihood of a customer to cancel their policy after filing a claim.

### Objectives

The goal of this project is to predict customer attrition within a line of business at Assurant, Connected Living. In particular, a model will predict hte probability of a customer canceling their policy after a certain period of time after a claim created by using claim attributes and possibly text as features, depending on the model performance without text


### Data

The primary dataset to be used consists of a table which has joined claim details and post-claim survey responses at a customer level.  The size of the data without excluding individuals who did not answer the open-ended question in the survey is over 250,000 records for three years’ worth of claims. The size is drastically reduced when considering only those who answered the open-ended question for building a model based on language and if we choose to limit the data range further. While exploring the data briefly, the cancel rate for a policy after a claim has been filed is approximately 20%. This percentage will vary based on the date range and other filters.

Among the questions present in the survey is one asking the customer how likely is it that they would recommend the product to someone else. The answer to this question is a number from 1 to 10, the net promoter score (NPS) rating. The open-ended question asks the customer to explain the reason behind the chosen NPS rating. Some of the attributes from the claim portion of the data include: whether the replacement device was new or not, device model shipped, loss type, scrutiny level, device model claimed, shipping method, deductible amount, time to approve, time to authorize, time to ship, and total claim time.

### Methods

The approach is to build a model using only the structured fields from the data first and then incorporate language to improve performance. Initially, a binary feature indicating whether the open-ended survey question was answered can be included. An SVM classifier among others will be evaluated. A starting point for using language as features is a bag of words (BoW) model. There is time available within the schedule of work to attempt a deep learning method but would probably need to collect more data.

### Results

Visualizations of results to be placed here.

### Conclusions

Conclusions here.

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```
