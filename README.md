# [PYTHON] Analyze Customer segmentation of SuperStore - a global retail company

## 1. Introduction
### 1.1. Business Context
SuperStore is a global retail company with a large customer base. For the upcoming Christmas and New Year season, the Marketing Department plans to run campaigns to show appreciation to customers who have supported the company over time, as well as to target potential customers who could become loyal.

However, the Marketing Department has not yet been able to segment the customers for this year because the dataset is too large to manually process as done in previous years. Therefore, they have asked the Data Analytics Department for assistance in implementing a customer segmentation model to tailor marketing campaigns for each customer group.

The Marketing Director has suggested using the RFM model, but in the past, when the company was smaller, the team could manually calculate and categorize customers using Excel. Now, with the growing volume of data, they would like the Data Department to develop a Python-based workflow to evaluate and segment customers.

The goal of this project is to apply the RFM model, developed with Python, to segment customers and recommend targeted marketing campaigns.\
The full Python code for this project can be found at: [View code](https://colab.research.google.com/drive/1SGRJx5Mqa6DhBUVCZ_9IAY9aNhHHdBIG#scrollTo=EmqsV049KgD-)
### 1.2. RFM Analysis
### Why RFM
- RFM is a marketing analysis technique that stands for Recency, Frequency, and Monetary.
  - **Recency**: measures how recently a customer has made a purchase.
  - **Frequency**: measures how often a customer has made purchases.
  - **Monetary**: measures the total amount of money a customer has spent on purchases.
- RFM is used to identify and categorize customers based on their purchasing behavior and how recently and frequently they have made purchases, as well as the monetary value of those purchases.
- RFM could be very useful, especially for small and medium-sized enterprises (SMEs) with limited marketing resources, helping them focus on the potentially right customer segments to increase ROI, reduce churn, reduce cost, improve customer relationship, and a lot more.

### How?
- In RFM analysis, customers are scored based on three factors (Recency - how recently, Frequency - how often, Monetary - how much), then labeled based on the combination of RFM scores.

### Reference
- [RFM Analysis For Successful Customer Segmentation](https://www.putler.com/rfm-analysis)

## 2. Data Understanding & EDA
## 3. Data Visualization with Python
- **Customer Profile by RFM Model**

![Image](https://github.com/user-attachments/assets/8897d439-c0e1-4b69-8171-540316ba0786)

- **Customer distribution based on Loyal status and Average purchase quantity thresholds**
  
![Image](https://github.com/user-attachments/assets/d57d97ac-289d-42dd-afe5-9a36879ac072)

- **Customer distribution based on Loyal status and Average spending thresholds**

![Image](https://github.com/user-attachments/assets/d76c83d3-4884-428b-b21d-d47cc36fbe11)

- **Proportion Revenue by Country**
  
![Image](https://github.com/user-attachments/assets/3814adaa-cf48-429e-8611-1e81dfcadd69)

## 3. Insights
- **At Risk** and **Cannot Lose Them** customer segments are crucial, as they represent the majority of customers and contribute significantly to revenue. However, their large proportion signals a potential risk. These customers have not engaged with the product for an extended period and are at a high risk of discontinuing its use.
- **Loyal**, **New Customers**, **Potential Loyalist**, and **Promising** groups make up the majority of customers. However, most of them have a low transaction value, resulting in only a modest contribution to overall revenue.
- **Loyal Customers** are group of customers whose number of quantity purchased in one order is not too large (<15 products in one transaction). This type of customer can be an individual who remains dedicated to the brand and contributes to long-term value. Their spending in one order is relatively small (under 18 USD per transaction). These customers often focus on lower-priced product segments but contribute to long-term value through repeat purchases.
- The largest market is the UK, which accounts for roughly 82% of the total revenue. Other potential markets are some European countries such as Netherlands, France, Germany.
## 4. Recommendations
- For **At Risk** and **Cannot Lose Them** customer segments, promotional campaigns or targeted announcements can be used to encourage customers to re-engage with the product.
- Implementing campaigns that encourage increased spending is essential for **Loyal**, **New Customers**, **Potential Loyalist**, and **Promising** groups.
- Use targeted advertising, marketing initiatives, and promotional strategies to engage potential customers and guide them toward becoming part of the loyal customer segment.
- Keep focusing on the UK market, implement sales and marketing campaigns in some European countries to boost customer spending.
