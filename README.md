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


### 2. What gender brought in the most sales?

```SQL
SELECT Gender, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY Gender
ORDER BY SUM(Amount) DESC
LIMIT 1;
```

### 3. What product did the male customer buy the most?

```SQL
SELECT ItemPurchased, SUM(Amount) AS "Total Amount"
FROM store_sales
WHERE Gender = 'Male'
GROUP BY ItemPurchased
ORDER BY SUM(AMOUNT) DESC
LIMIT 1;
```

### 4. What was the top 4 purchased item?

```SQL
SELECT ItemPurchased, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY ItemPurchased
ORDER BY SUM(Amount) DESC
LIMIT 4;
```

### 5. What season brought in sales of over 370000?

```SQL
SELECT Season, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY Season
HAVING SUM(Amount) > 370000;
```

### 6. Did the customers pay by cash the most, or by payment on delivery?

```SQL
SELECT PaymentMethod, SUM(Amount) AS "Total Amount"
FROM store_sales
GROUP BY PaymentMethod
ORDER BY SUM(Amount) DESC
LIMIT 1;
```

### 7. What gender paid with cash on delivery the most?

```SQL
SELECT PaymentMethod, Gender, SUM(Amount) AS "Total Amount"
FROM store_sales
WHERE PaymentMethod = 'Cash on Delivery'
GROUP BY Gender
ORDER BY SUM(Amount) DESC
LIMIT 1;
```

### 8. What season of the year did the female customers shop the most?

```SQL
SELECT Season, SUM(Amount) AS "Total Amount"
FROM store_sales
WHERE Gender = 'Female'
GROUP BY Season
ORDER BY SUM(Amount) DESC
LIMIT 1;
```

### 9. Which gproduct rated the lowest?

```SQL
SELECT ItemPurchased, ItemRating
FROM store_sales
ORDER BY ItemRating
LIMIT 1;
```

### 10. Which gender has the most previous purchases?

```SQL
SELECT Gender, COUNT(PreviousPurchases) AS "Previous Purchase"
FROM store_sales
GROUP BY Gender
ORDER BY COUNT(PreviousPurchases) DESC
LIMIT 1;
```

### 11. What gender got the most dumbbells?

```SQL
SELECT  Gender, Sum(Amount)
FROM store_sales
WHERE ItemPurchased = 'Dumbbells'
GROUP BY Gender
ORDER BY SUM(Amount) DESC
LIMIT 1;
```
