# Customer-Segmentation-and-Product-Recommendation

## Overview
This project focuses on customer segmentation and a hybrid recommendation system using machine learning techniques. It involves clustering customers based on their purchase behavior and demographic details and providing personalized product recommendations using collaborative and content-based filtering.

## Dataset
The dataset includes customer purchase history, product metadata, and user demographics. Key columns include:
- User ID
- Product ID
- Product Name
- Category
- Price
- Purchase Date
- Quantity
- Total Spending
- Clicks
- Time Spent
- Abandoned Cart
- Engagement Score
- Age
- Gender
- Location
- Income

## Steps

### 1. Data Preprocessing
Data is cleaned, missing values are handled, and necessary transformations are applied. Features are selected based on relevance to customer segmentation and recommendation tasks.

### 2. Customer Segmentation
Customers are grouped using K-Means clustering based on their total spending, purchase frequency, age, and income. The elbow method is used to determine the optimal number of clusters. The final clustering results are visualized and saved for further analysis.

### 3. Recommendation System
A hybrid recommendation approach is implemented combining collaborative filtering with content-based filtering.

#### Collaborative Filtering
- The LightFM model is used to predict user-product interactions based on previous purchases.
- The dataset is transformed into an interaction matrix where rows represent users and columns represent products.
- The model is trained using Weighted Approximate-Rank Pairwise (WARP) loss for ranking optimization.

#### Content-Based Filtering
- TF-IDF is applied to product descriptions to extract textual features.
- Cosine similarity is used to find similar products based on text features.

#### Hybrid Approach
- The collaborative filtering model generates initial recommendations.
- Content-based filtering refines these recommendations by finding similar products.
- The final recommendation list is a combination of both methods, ensuring diversity and relevance.

## Evaluation
The recommendation system is evaluated using precision at k and AUC score. The trained LightFM model achieves the following results:
- Precision at k: 0.4164
- AUC score: 0.9251

## Deployment
The trained model and mappings are saved for future use. The recommendation system can be reloaded and used to generate predictions without retraining.

## Installation and Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/customer-segmentation-recommendation.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook or script to process data and train models.
4. Use the provided functions to generate recommendations for users.

## Future Improvements
- Fine-tuning clustering parameters for better segmentation.
- Incorporating additional features such as browsing history for enhanced recommendations.
- Deploying the model as an API for real-time recommendations.

## Acknowledgments
Special thanks to open-source libraries such as LightFM, scikit-learn, pandas, and seaborn for making this project possible.

