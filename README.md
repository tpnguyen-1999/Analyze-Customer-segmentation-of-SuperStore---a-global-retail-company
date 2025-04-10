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
### Dataset Overview
- ecommerce retail
  
|  |InvoiceNo|	StockCode|	Description|	Quantity|	InvoiceDate|	UnitPrice|	CustomerID|	Country|
|--|---------|-----------|-------------|----------|------------|-----------|------------|--------|
|0|	536365|	85123A|	WHITE HANGING HEART T-LIGHT HOLDER|	6|	2010-12-01 08:26:00|	2.55|	17850.0|	United Kingdom|
|1|	536365|	71053|	WHITE METAL LANTERN|	6|	2010-12-01 08:26:00|	3.39|	17850.0|	United Kingdom|
|2|	536365|	84406B|	CREAM CUPID HEARTS COAT HANGER|	8|	2010-12-01 08:26:00|	2.75|	17850.0|	United Kingdom|
|3|	536365|	84029G|	KNITTED UNION FLAG HOT WATER BOTTLE|	6|	2010-12-01 08:26:00|	3.39|	17850.0|	United Kingdom|
|4|	536365|	84029E|	RED WOOLLY HOTTIE WHITE HEART.|	6|	2010-12-01 08:26:00|	3.39|	17850.0|	United Kingdom|
|...|	...|	...|	...|	...|	...|	...|	...|	...|
|541904|	581587|	22613|	PACK OF 20 SPACEBOY NAPKINS|	12|	2011-12-09 12:50:00|	0.85|	12680.0|	France|
|541905|	581587|	22899|	CHILDREN'S APRON DOLLY GIRL|	6|	2011-12-09 12:50:00|	2.10|	12680.0|	France|
|541906|	581587|	23254|	CHILDRENS CUTLERY DOLLY GIRL|	4|	2011-12-09 12:50:00|	4.15|	12680.0|	France|
|541907|	581587|	23255|	CHILDRENS CUTLERY CIRCUS PARADE|	4|	2011-12-09 12:50:00|	4.15|	12680.0|	France|
|541908|	581587|	22138|	BAKING SET 9 PIECE RETROSPOT|	3|	2011-12-09 12:50:00|	4.95|	12680.0|	France|

- Segmentation

|   |Segment|	RFM Score|
|---|-------|----------|
|0|	Champions|	555, 554, 544, 545, 454, 455, 445|
|1|	Loyal|	543, 444, 435, 355, 354, 345, 344, 335|
|2|	Potential Loyalist|	553, 551, 552, 541, 542, 533, 532, 531, 452, 4...|
|3|	New Customers|	512, 511, 422, 421, 412, 411, 311|
|4|	Promising|	525, 524, 523, 522, 521, 515, 514, 513, 425,42...|
|5|	Need Attention|	535, 534, 443, 434, 343, 334, 325, 324|
|6|	About To Sleep|	331, 321, 312, 221, 213, 231, 241, 251|
|7|	At Risk|	255, 254, 245, 244, 253, 252, 243, 242, 235, 2...|
|8|	Cannot Lose Them|	155, 154, 144, 214,215,115, 114, 113|
|9|	Hibernating customers	332, 322, 233, 232, 223, 222, 132, 123, 122, 2...|
|10|	Lost customers|	111, 112, 121, 131,141,151|

### Key Takeaways and Data Cleaning
- InvoiceNo: no problem
- StockCode: no problem
- Description: 1454 missing values
- Quantity: remove negative values
- InvoiceDate: no problem
- UnitPrice: remove negative values
- CustomerID: 135080 missing values -> remove rows with no CustomerID
- Country: no problem
- Remove duplicates

### Adding RFM values


## 3. Data Visualization with Python
### 3.1. Customer Profile by RFM Model

![Image](https://github.com/user-attachments/assets/8897d439-c0e1-4b69-8171-540316ba0786)

- **At Risk** and **Cannot Lose Them** customer segments are crucial, as they represent the majority of customers and contribute significantly to revenue. However, their large proportion signals a potential risk. These customers have not engaged with the product for an extended period and are at a high risk of discontinuing its use.
- **Loyal**, **New Customers**, **Potential Loyalist**, and **Promising** groups make up the majority of customers. However, most of them have a low transaction value, resulting in only a modest contribution to overall revenue.

### 3.2. Customer distribution based on Loyal status and Average purchase quantity thresholds
  
![Image](https://github.com/user-attachments/assets/d57d97ac-289d-42dd-afe5-9a36879ac072)

- **Loyal Customers** are group of customers whose number of quantity purchased in one order is not too large (<15 products in one transaction). This type of customer can be an individual who remains dedicated to the brand and contributes to long-term value. 

### 3.3. Customer distribution based on Loyal status and Average spending thresholds

![Image](https://github.com/user-attachments/assets/d76c83d3-4884-428b-b21d-d47cc36fbe11)

- **Loyal Customers** are group of customers whose spending in one order is relatively small (under 18 USD per transaction). These customers often focus on lower-priced product segments but contribute to long-term value through repeat purchases.

### 3.3. Proportion Revenue by Country
  
![Image](https://github.com/user-attachments/assets/3814adaa-cf48-429e-8611-1e81dfcadd69)

- The largest market is the UK, which accounts for roughly 82% of the total revenue. Other potential markets are some European countries such as Netherlands, France, Germany.

## 4. Recommendations
- For **At Risk** and **Cannot Lose Them** customer segments, promotional campaigns or targeted announcements can be used to encourage customers to re-engage with the product.
- Implementing campaigns that encourage increased spending is essential for **Loyal**, **New Customers**, **Potential Loyalist**, and **Promising** groups.
- Use targeted advertising, marketing initiatives, and promotional strategies to engage potential customers and guide them toward becoming part of the loyal customer segment.
- Keep focusing on the UK market, implement sales and marketing campaigns in some European countries to boost customer spending.
