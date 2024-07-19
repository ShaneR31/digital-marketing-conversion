# Digital Marketing Campaign Analysis

![Title Image](/graphics/title.jpg)

## Introduction
This project focuses on analyzing and optimizing digital marketing strategies using a comprehensive dataset that includes customer demographics, engagement metrics, and campaign interactions. The goal is to understand the key factors driving customer conversions, segment customers for targeted marketing, and evaluate the effectiveness of various marketing campaigns. The full notebook and analysis can be found [here](https://shanereichlin.com/digital-marketing-conversion/docs/digital_marketing_conversion.html).

## Exploratory Data Analysis (EDA)
We started by performing exploratory data analysis to understand the distribution and relationships of the features in our dataset:
- **Numerical Features**: Key features such as Age, Income, AdSpend, ConversionRate, and WebsiteVisits were visualized to understand their distributions. Most features showed relatively uniform distributions, indicating a diverse customer base and varied marketing efforts.

![Numerical Features Distribution](/graphics/numDists.png)

- **Categorical Features**: Features like Gender, CampaignChannel, and CampaignType were analyzed to understand the composition of the dataset. The analysis showed a balanced use of different marketing channels and campaign types.

![Categorical Features Distribution](/graphics/catDists.png)

## Feature Engineering
We created new features to enhance the predictive power of our model, these include:
- **EmailEngagement**: Combined email opens and clicks.
- **SiteEngagement**: Combined website visits, pages per visit, and time on site.
- **IncomePerClick**: Income divided by click-through rate.
- **AdSpendPerClick**: Ad spend divided by click-through rate.
- **ClickToConversionRate**: Conversion rate divided by click-through rate.
- **TotalInteractions**: Aggregated social shares, email opens, email clicks, and previous purchases.

## Correlation Analysis
A correlation matrix was created to identify relationships between features. The analysis revealed the following key insights related to conversion:
- **Positive Correlations**:
  - **EmailEngagement and Conversion**: Higher engagement with email campaigns is strongly associated with higher conversion rates.
  - **SiteEngagement and Conversion**: Increased interaction with the website correlates positively with conversion likelihood.
  - **PreviousPurchases and Conversion**: Customers with a history of previous purchases are more likely to convert again.

- **Negative Correlations**:
  - **AdSpendPerClick and Conversion**: Higher ad spend per click showed a weaker, negative correlation with conversion, indicating that simply increasing ad spend may not directly lead to higher conversions.

![Correlation Matrix](/graphics/corrMatrix.png)

## Predicting Customer Conversion
### Data Preprocessing
We applied SMOTE to handle class imbalance in the target variable (Conversion) and performed feature scaling using MinMaxScaler.
### Model Training
We trained an XGBoost classifier and performed hyperparameter tuning using GridSearchCV. The best model demonstrated strong performance with high precision, recall, and F1 scores.
### Model Evaluation
The final model's performance was evaluated using various metrics:

| Model   | Accuracy | Precision | Recall   | F1 Score | ROC AUC |
|---------|----------|-----------|----------|----------|---------|
| XGBoost | 0.927917 | 0.927402  | 0.995722 | 0.960348 | 0.803918|

![Confusion Matrix](/graphics/confusionMatrix.png)

- **Confusion Matrix**: High true positives and low false negatives indicated the model's effectiveness in predicting conversions.

![ROC Curve](/graphics/roc.png)

- **ROC Curve**: The AUC value of 0.80 indicated good performance in distinguishing between converted and non-converted customers.

## Customer Segmentation
### Clustering Analysis
We used K-Means clustering to segment customers based on engagement and demographic features. The clusters were visualized using PCA, and the analysis revealed distinct customer segments, allowing for tailored marketing strategies.

![PCA Clusters](/graphics/pca.png)

### Cluster Evaluation
- **Silhouette Score**: 0.19
- **Davies-Bouldin Score**: 1.73
- **Calinski-Harabasz Score**: 1725.85

The scores indicated reasonable cluster separation but also highlighted areas for improvement.


## Campaign Effectiveness
We analyzed the effectiveness of different campaign channels and types:
- **Campaign Channels**: Email, PPC, and Social Media showed high conversion rates.

- **Campaign Types**: Conversion campaigns were the most effective, followed by Awareness and Retention campaigns.


## Future Work
Several areas for future exploration were identified:
- **Feature Engineering**: Additional interaction features and external data sources could further improve model performance and clustering results.
- **Advanced Clustering Techniques**: Techniques like DBSCAN or Gaussian Mixture Models may provide better cluster separation and interpretability.
- **A/B Testing**: Implementing A/B testing strategies can optimize marketing efforts in areas such as email campaigns, ad campaigns, website engagement, loyalty programs, conversion rate optimization, content marketing, and referral programs.


## Conclusion
This project provided valuable insights into customer behavior and marketing strategies. The predictive model, customer segmentation, and campaign effectiveness analysis offer a comprehensive approach to optimizing digital marketing efforts. Future work will focus on refining these strategies through advanced techniques and A/B testing to drive even greater marketing success.

## Links
- [Project Notebook](https://shanereichlin.com/digital-marketing-conversion/docs/digital_marketing_conversion.html)
- [Project Repository](https://github.com/ShaneR31/digital-marketing-conversion)