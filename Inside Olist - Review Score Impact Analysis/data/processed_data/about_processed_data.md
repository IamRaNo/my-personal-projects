# Olist Review & Order-Level Dataset

This dataset contains **99,224 order-level records** with engineered features for analyzing customer reviews, product characteristics, delivery performance, and payment behavior. It is suitable for exploratory data analysis, modeling customer satisfaction, and understanding operational factors behind review outcomes.

---
## 📦 Dataset Overview

- **Total rows:** 99,224  
- **Total columns:** 18  
- **Memory usage:** ~13.6 MB  

Each row represents a **unique order-review pair**, enriched with product, payment, logistics, and customer-behavior features.

---

## 🧾 Column Dictionary

### 1. **review_score** *(int)*  
Customer’s rating for the order (1–5).

### 2. **review_creation_date** *(object)*  
Date when the customer submitted the review.

### 3. **total_unique_products** *(int)*  
Number of distinct products in the order.

### 4. **total_products** *(int)*  
Total product quantity purchased in the order.

### 5. **avg_price** *(float)*  
Average price of items in the order.

### 6. **avg_freight** *(float)*  
Average freight charge paid for items.

### 7. **is_multiple_seller** *(int: 0/1)*  
Indicates whether the order involved multiple sellers.

### 8. **max_attempt** *(int)*  
Maximum number of attempted payment attempts for this order.

### 9. **payment_type_used** *(int)*  
How many unique payment type was used.

### 10. **installment_duration** *(int)*  
Number of installments chosen by the customer.

### 11. **total_paid_value** *(float)*  
Total amount paid for the order.

### 12. **order_status** *(object)*  
Final status of the order (delivered, canceled, shipped, etc.).

### 13. **approval_time** *(float)*  
Time (in days) between purchase and order approval.  
Contains **156 missing values**.

### 14. **delivery_time** *(float)*  
Actual delivery duration.  
Contains **2,865 missing values**.

### 15. **delivery_delay** *(float)*  
Difference between actual and estimated delivery time.  
Positive = delayed, Negative = early.  
Missing for the same rows as `delivery_time`.

### 16. **product_id** *(float)*  
How many products were ordered in that order.  
**759 missing values** due to missing product records.

### 17. **product_category_name** *(float/object)*  
How many product categories ordered. 
Same missing count as `product_id`.

### 18. **dimensional_weight** *(float)*  
Total dimensional weight across all products in the order.

---

## 🧹 Missing Data Summary

| Column | Missing | Reason |
|--------|---------|--------|
| approval_time | 156 | Order is not approved yet |
| delivery_time | 2,865 | Order not delivered yet |
| delivery_delay | 2,865 | delivery is not done yet |
| product_id | 759 | No products were ordered,mainly cancelled orders |
| product_category_name | 759 | Missing category info |

---

## 🧠 Suitable Use Cases

- Review score prediction  
- Delivery delay impact analysis  
- Customer experience analytics  
- Product-level feature engineering  
- Logistic & operational insights  
- Price/freight sensitivity studies  

---

## 📌 Notes

- Ensure date columns are converted to proper datetime format.  
- Encoded variables (payment type, category) may require decoding for interpretation.  
- Rows with missing delivery information belong to orders not delivered or cancelled.

---

