# eCommerce Customer Segmentation and Clustering

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)
![Libraries](https://img.shields.io/badge/Libraries-Pandas%20%7C%20Scikit--learn%20%7C%20Seaborn-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## Overview

This project focuses on analyzing an eCommerce transactions dataset to derive actionable business insights, segment customers based on their behavior, and build a lookalike model for targeted marketing. By leveraging data science techniques, we aim to understand customer purchasing patterns, identify distinct customer groups, and provide data-driven recommendations to enhance business strategy.

The project is divided into three core tasks:
1.  **Exploratory Data Analysis (EDA)** to uncover trends and insights.
2.  **Customer Segmentation** using clustering algorithms to group similar customers.
3.  **Lookalike Modeling** to find customers similar to a given user profile.

## Dataset

The dataset consists of three CSV files capturing customer information, product details, and transaction records.

*   **`Customers.csv`**: [Download Link](https://drive.google.com/file/d/1bu_--mo79VdUG9oin4ybfFGRUSXAe-WE/view?usp=sharing)
    *   `CustomerID`: Unique identifier for each customer.
    *   `CustomerName`: Name of the customer.
    *   `Region`: Continent where the customer resides.
    *   `SignupDate`: Date when the customer signed up.

*   **`Products.csv`**: [Download Link](https://drive.google.com/file/d/1IKuDizVapw-hyktwfpoAoaGtHtTNHfd0/view?usp=sharing)
    *   `ProductID`: Unique identifier for each product.
    *   `ProductName`: Name of the product.
    *   `Category`: Product category.
    *   `Price`: Product price in USD.

*   **`Transactions.csv`**: [Download Link](https://drive.google.com/file/d/1saEqdbBB-vuk2hxoAf4TzDEsykdKlzbF/view?usp=sharing)
    *   `TransactionID`: Unique identifier for each transaction.
    *   `CustomerID`: ID of the customer who made the transaction.
    *   `ProductID`: ID of the product sold.
    *   `TransactionDate`: Date of the transaction.
    *   `Quantity`: Quantity of the product purchased.
    *   `TotalValue`: Total value of the transaction.

---

## Exploratory Data Analysis & Business Insights

EDA was performed to understand the underlying patterns in the data. EDA analysis can be found in the EDA.ipynb notebook above. The analysis yielded several key business insights that can inform strategic decisions.

### Key Business Insights

1.  **Rise of Aesthetics in North America**: North American customers show a strong preference for decorative Home Decor items like **Wall Art** and **Vases** over purely functional products, suggesting a market that values aesthetics.
    *   **Recommendation**: Increase the marketing focus and inventory for decorative items in North America.

2.  **Missed Holiday Opportunity for Books**: Book sales see a significant drop from September to November, a period that is typically a high-consumption holiday season for other categories.
    *   **Recommendation**: Launch targeted holiday promotions, gift bundles, and marketing campaigns to position books as ideal holiday gifts.

3.  **Seasonal Mismatch in Asian Clothing Market**: Despite high summer temperatures in Asia, sales of summer clothing are low. Winter items like **Sweaters** and **Jackets** surprisingly outperform T-shirts.
    *   **Recommendation**: Re-evaluate the clothing catalog for Asia to better align with local demand, potentially increasing the availability and promotion of summer-friendly apparel.

4.  **Decline in North American Electronics Holiday Sales**: Unlike other regions, Electronics sales in North America decline during the holiday season (November-December).
    *   **Recommendation**: Revise holiday marketing campaigns for electronics in North America to highlight gifting options, discounts, and tech bundles more effectively.

5.  **Weak Winter Clothing Sales in South America**: Clothing is the lowest-performing category in South America (19.3% of sales), with particularly weak sales during the winter months.
    *   **Recommendation**: Reassess the winter clothing lineup for South America to introduce designs and fabrics better suited for the region's moderate winter climate.

---

## Customer Segmentation / Clustering

Customer segmentation was performed to group customers based on their profile and transaction history. Two clustering algorithms were evaluated: K-Means and Gaussian Mixture Models (GMM). The Code for Customer Clustering will be available at Clusltering.ipynb

### Methodology
*   Features were engineered from customer and transaction data, including total transactions, average transaction value, and preferred product categories.
*   The Elbow Method was used to determine the optimal number of clusters for K-Means.
*   Both models were trained on the engineered feature set.

### Results
GMM was identified as the superior model for this dataset based on clustering evaluation metrics.

*   **Algorithm Chosen**: Gaussian Mixture Model (GMM)
*   **Number of Clusters**: 5
*   **Davies-Bouldin (DB) Index**: **0.68** (lower is better)
*   **Silhouette Score**: **0.52** (higher is better)

GMM provided more compact and well-separated clusters, effectively capturing the relationships between categorical features like `MostBoughtCategory`.

---

## Lookalike Model

A lookalike model was developed to identify customers with similar profiles and purchasing behaviors. This model takes a `CustomerID` as input and returns the top 3 most similar customers along with a similarity score.

### Methodology
The model defines similarity based on a combination of customer profile information (Region) and transaction history (total transactions, average spend, and product preferences). A similarity score is calculated for all other customers, and the top 3 are recommended.

*(Further details on the model's logic and implementation can be found in the Lookalike_Model.ipynb)*

---

## Technical Stack

*   **Language**: Python 3.9
*   **Libraries**:
    *   `pandas` for data manipulation and analysis.
    *   `numpy` for numerical operations.
    *   `scikit-learn` for clustering (K-Means, GMM) and preprocessing.
    *   `matplotlib` & `seaborn` for data visualization.
    *   `Jupyter Notebook` for interactive development and analysis.