## [Modeling Customer Attrition Based on Post-Event Insurance Data](https://github.com/cschubert29/DSCapstone/blob/master/IDC_6940_Final_Report___CSchubert.pdf)

Customer attrition, or the loss of customers, is used as a key performance indicator across several industries, including insurance. The insurance industry’s customer acquisition costs are high, so it is important to retain existing customers rather than only focus on getting new ones. The distribution of resources for both customer retention and acquisition can be improved by being able to predict the likelihood of a customer to cancel their policy after filing a claim.

### Objectives

The key goal of this project was to answer the following questions:
* Is it feasible to model customer attrition using claim data and achieve actionable results?
* Can specific attributes associated with high likelihood of attrition be derived?

Model performance was evaluated against a baseline and feature importance analysis was conducted to determine the attributes that contribute to attrition.

### Data

The primary dataset consists of the set of customers who both filed a claim and completed a post-claim survey asking them questions about their experience.  Some of the attributes from the claim portion of the data include: claim status, device model claimed, device model shipped, whether the replacement device was new or not, loss type, scrutiny level, shipping method, deductible amount, and total claim time.

The secondary dataset was created to use as input to a sequential classifier. The structure of the data differs from the main dataset in that we have multiple rows per enrollment, or customer. Since a customer can file multiple claims, the dataset has  multiple rows per enrollment, one for each claim filed. 

### Methods

The approach is to build a model using only the structured fields from the data first and then incorporate language to improve performance. 
- Bag of words (BoW) & TF-IDF based models (unigrams/bigrams/trigrams/skip-grams tested)
- Deep learning
--Pre-trained embeddings (Google Word2Vec, GLOVE)
--Embeddings trained on domain data
- Combined model (structured data + features from text)
- Sequential classifier (RNN)

### Results

![Table10.PNG](/assets/img/Table10.PNG)

![Table7.png](/assets/img/Table7.png)

![FeatureImp1](/assets/img/FeatureImp1.png#left)

![FeatureImp2](/assets/img/FeatureImp2.png#right)

Based on gain, the most important features from the first figure are: Answer 1; Loss = physical damage; Non-new
replacement device; and Deductible amount. The most important features from the second figure are: Carrier = Samsung or
T-Mobile; and the following TF-IDF terms: "cancel", "scam"," f***", and "apple." Other important features
are low scrutiny count and total claim time.

### Conclusions

* Contributed a developed model
* An augmented key driver analysis for attrition which includes external data sources and significant TF-IDF terms
* Model did not  achieve start of art F1 score but is better than the most frequent baseline
* Important features can be used to make recommendations to the claims operations and customer experience teams on how to improve and prevent attrition
* Further work can entail working on carrier-specific models and rule-based methods for driving customer continuity management
