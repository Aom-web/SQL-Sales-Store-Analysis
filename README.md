## Sales-Store-Analysis-SQL
## Overview
Analysis of a sales store performance using SQL Query based on factors such as category, gender, itempurchased, season, profit and basically communicating with the dat set.
## Data Source
The data was gotten from Kaggle
[Download here] (https://www.kaggle.com/datasets/hassanjameelahmed/store-sales)

## SQL Queries
### 1. What category brought in the most sales?

```SQL
SELECT Category, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY Category
ORDER BY SUM(Amount) DESC
LIMIT 1;
```
<img width="206" height="53" alt="1" src="https://github.com/user-attachments/assets/df8f55dd-ca55-4c17-a3f7-4c9597b08867" />

### 2. Which gender brought in the most sales?

```SQL
SELECT Gender, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY Gender
ORDER BY SUM(Amount) DESC
LIMIT 1;
```
<img width="160" height="60" alt="2" src="https://github.com/user-attachments/assets/0eaa3ee2-4e46-463f-b128-fac21bf35a84" />

### 3. What product did the male customer buy the most?

```SQL
SELECT ItemPurchased, SUM(Amount) AS "Total Amount"
FROM store_sales
WHERE Gender = 'Male'
GROUP BY ItemPurchased
ORDER BY SUM(AMOUNT) DESC
LIMIT 1;
```
<img width="202" height="57" alt="3" src="https://github.com/user-attachments/assets/063585b9-213b-44ca-852f-5e08967a3328" />


### 4. What was the top 4 purchased item?

```SQL
SELECT ItemPurchased, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY ItemPurchased
ORDER BY SUM(Amount) DESC
LIMIT 4;
```
<img width="222" height="138" alt="4" src="https://github.com/user-attachments/assets/0b2c890f-fa1d-4ea2-ba2e-d7fd5c860b76" />


### 5. What season brought in sales of over 370000?

```SQL
SELECT Season, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY Season
HAVING SUM(Amount) > 370000;
```
<img width="171" height="59" alt="5" src="https://github.com/user-attachments/assets/331f3786-16e6-4f33-9526-7174361c14cc" />


### 6. Did the customers pay by cash the most, or by payment on delivery?

```SQL
SELECT PaymentMethod, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY PaymentMethod
ORDER BY SUM(Amount) DESC
LIMIT 1;
```
<img width="213" height="59" alt="6" src="https://github.com/user-attachments/assets/141fc5b5-366b-4a1f-8c30-96ec3169d76c" />


### 7. Which gender paid with cash on delivery the most?

```SQL
SELECT PaymentMethod, Gender, SUM(Amount) AS "Total Amount"
FROM store_sales
WHERE PaymentMethod = 'Cash on Delivery'
GROUP BY Gender
ORDER BY SUM(Amount) DESC
LIMIT 1;
```
<img width="298" height="53" alt="7" src="https://github.com/user-attachments/assets/d70b40bd-2557-46f6-a5d6-d16a54daa6f1" />


### 8. What season of the year did the female customers shop the most?

```SQL
SELECT Season, SUM(Amount) AS "Total Amount"
FROM store_sales
WHERE Gender = 'Female'
GROUP BY Season
ORDER BY SUM(Amount) DESC
LIMIT 1;
```
<img width="167" height="61" alt="8" src="https://github.com/user-attachments/assets/2aebb659-3196-4423-915e-5dbd5edfad20" />


### 9. What product rated the lowest?

```SQL
SELECT ItemPurchased, ItemRating
FROM store_sales
ORDER BY ItemRating
LIMIT 1;
```
<img width="195" height="57" alt="9" src="https://github.com/user-attachments/assets/064e6302-6ae4-48e7-aab8-e4683307c0aa" />

### 10. Which gender has the most previous purchases?

```SQL
SELECT Gender, COUNT(PreviousPurchases) AS "Previous Purchase"
FROM store_sales
GROUP BY Gender
ORDER BY COUNT(PreviousPurchases) DESC
LIMIT 1;
```
<img width="190" height="53" alt="10" src="https://github.com/user-attachments/assets/27c7af8a-aed6-4ec1-8b72-2ca841af5e6a" />

### 11. Which gender got the most dumbbells?

```SQL
SELECT  Gender, Sum(Amount)
FROM store_sales
WHERE ItemPurchased = 'Dumbbells'
GROUP BY Gender
ORDER BY SUM(Amount) DESC
LIMIT 1;
```
<img width="167" height="58" alt="11" src="https://github.com/user-attachments/assets/453439ac-eedd-486c-9969-acce1e97ec09" />
