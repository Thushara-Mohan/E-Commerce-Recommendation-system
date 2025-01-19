# E-Commerce-Recommendation-system

Amazon Product Analysis and Recommendation system (content based filtering)

In this Data Science project, I analyzed a dataset of over 1,000 products listed on Amazon and built a recommendation system for these products.

The dataset includes details such as product name, category, price, rating, and user reviews. My goal was to understand customer preferences, identify purchasing patterns, and develop a recommendation system to suggest products to users based on their interests.

The project consisted of the following steps:

#### 1. Data collection: 
I collected the Amazon products dataset from Kaggle.
#### 2. Data preparation: 
I cleaned and preprocessed the dataset for analysis.
#### 3. Exploratory data analysis and Visualization: 
I analyzed the data to understand the distribution of products by categories, customer ratings, and reviews.I also visualized the data to identify trends and patterns.
#### 5. Simple recommendation system: 
I developed a recommendation system using machine learning algorithms to suggest products to users based on their interests and previous purchases.

## 1. Data Collection:
The dataset contains information on over 1,000 products sold on Amazon, including their names, categories, prices, ratings, and reviews. This data offers valuable opportunities to understand customer preferences and product performance.  

From Amazon's perspective, analyzing this data can help identify popular products, refine pricing strategies, and improve marketing efforts. For customers, insights from this data make it easier to find highly rated, positively reviewed products, helping them make informed purchasing decisions.  

In this project, I’ll dive into the dataset, conduct data analysis and visualization, and develop a recommendation system to suggest products based on user interests and purchase history.  

## Features of the Dataset  

- **product_id**: Unique identifier for each product  
- **product_name**: Name of the product  
- **category**: Product category  
- **discounted_price**: Discounted price of the product  
- **actual_price**: Original price of the product  
- **discount_percentage**: Percentage of discount offered  
- **rating**: Product rating  
- **rating_count**: Number of reviews contributing to the rating  
- **about_product**: Product description  
- **user_id**: ID of the user who wrote a review  
- **user_name**: Name of the user who wrote a review  
- **review_id**: Unique identifier for each review  
- **review_title**: Title of the review  
- **review_content**: Full content of the review  
- **img_link**: URL of the product image  
- **product_link**: URL to the product’s official page  

To access the dataset, visit the Kaggle website: [Amazon Sales Dataset on Kaggle](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset).

## 2. Data preparation:
Before starting the analysis, I ensured that the dataset was clean and properly formatted to enhance its reliability and usability. The preparation process included the following steps:  

- **Data Inspection and Cleaning**:
    - I inspected the dataset for missing values, duplicate entries, and inconsistent data.
    - Rows with incomplete information were removed using the `dropna()` function, ensuring that only complete and accurate data remained for analysis. 
    - Duplicate rows were also identified and eliminated to avoid redundancy. 
    - Additionally, I adjusted data types, such as converting price columns from strings to numeric types, to enable proper calculations.  

- **Feature Engineering and Transformation**: 
    - New columns were created to enrich the dataset. For instance, a "rating_weighted" column was added to combine both the average rating and the number of ratings, giving more importance to products with many positive reviews.
    - I also extracted the main and subcategories from the category column to provide better insights into product distribution.
    - This step offered a clearer understanding of trends within broader and more specific categories, enabling more meaningful data visualizations and analysis.  

These steps ensured the dataset was clean, comprehensive, and ready for exploratory data analysis and the development of the recommendation system.

## 3. Exploratory Data Analysis and Visualization

In this step, we explored the dataset to uncover meaningful insights about product trends, customer preferences, and overall market behavior. Here’s a summary of our findings and analysis:  

- **Product Distribution**:  
   - Analyzed how products are distributed across various categories and subcategories.  
   - Identified popular categories like *Electronics, Home & Kitchen, and Computers & Accessories* while noting areas of lower demand.  

- **Customer Ratings**:  
   - Visualized rating trends to understand customer satisfaction.  
   - Observed that most ratings fall within the 3-5 range, indicating overall positive feedback but room for improvement.  

- **Customer Reviews**:  
   - Generated word clouds to highlight common themes and sentiments expressed in reviews.  
   - Identified frequently mentioned product features and areas for enhancement.  

- **Statistical Relationships**:  
   - Investigated correlations between features like price, ratings, and discounts.  
   - Found that pricing strategies and discounts significantly impact customer choices in certain categories.  

These insights provide a comprehensive understanding of customer behavior and help businesses refine their product offerings, marketing strategies, and pricing models to better align with market demands.

## 4. Recommendation system:
The main part of this project implements a product recommendation system that suggests products to users based on their browsing history and the similarity of product features. The system uses machine learning techniques such as Label Encoding and TF-IDF Vectorization to analyze the product and user data.

#### **Features**:
1. **User ID Encoding**: 
   - The `user_id` is encoded into numerical values using `LabelEncoder` from `sklearn.preprocessing`.
   - This helps to handle categorical variables (user IDs) efficiently.
   - A frequency table of user IDs is generated to show the number of occurrences of each user in the dataset.

2. **Data Preparation**: 
   - The `product_name` and `category` columns are combined to create a new feature, `combined_features`, which will be used for calculating similarity.
   
3. **TF-IDF Vectorization**: 
   - `TfidfVectorizer` is used to convert the text data (combined features) into numerical vectors.
   - This method assigns weights to terms based on their frequency in the document and their importance across all documents, enabling better similarity calculations.

4. **Cosine Similarity**:
   - Cosine similarity is used to calculate how similar the products are to each other based on their `combined_features`.
   - This technique measures the cosine of the angle between two vectors, where a higher cosine similarity indicates more similarity.

5. **Recommendation Function**:
   - The `recommend_products()` function recommends products to a specific user based on their browsing history.
   - The function returns a list of the top N most similar products to the one the user interacted with.
   
6. **Example Usage**:
   - The system expects a valid `user_id` (from the dataset) to generate personalized recommendations.
   - The recommended products are displayed for a given user based on similarity scores calculated through cosine similarity.

#### **How to Use**:
1. **Dataset**: Ensure that the dataset contains product-related columns such as `user_id`, `product_name`, and `category`. The recommendation system works with this dataset to generate personalized recommendations.
   
2. **Run the Code**:
   - Load the dataset (`df`) and run the code to generate recommendations for any given user ID.
   - Example: Replace `'user123'` in the code with a valid `user_id` from the dataset.
   
3. **Output**: 
   - The system will output a list of product names that are most similar to the product that the given user interacted with, based on the product’s features.

#### **Example Output**:
```
Recommended Products:
- Smartwatch X3000
- 4K UHD Smart Television
- Wireless Bluetooth Earbuds
- Gaming Laptop Z5000
- Noise Cancelling Headphones 7X
```

This recommendation system helps businesses suggest relevant products to customers by analyzing their past interactions and the features of the products they viewed or purchased. It enhances the user experience by personalizing suggestions and improving sales opportunities.











