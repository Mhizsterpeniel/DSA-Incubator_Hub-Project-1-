## Project Topic: Amazon Product Review Analysis.
### Project Overview
You are working as a Junior Data Analyst at RetailTech Insights, a company that provides e-commerce 
analytics solutions to sellers on platforms like Amazon. Your team has been tasked with analysing 
product and customer review data to generate insights that can guide product improvement,
marketing strategies, and customer engagement.

### Dataset Description
The dataset contains information scraped from Amazon product pages, 
including:
- Product details: name, category, price, discount, and ratings
- Customer engagement: user reviews, titles, and content
- Each row represents a unique product, with aggregated reviewer data stored as comma-separated values

##### Total Records: 1,465 rows TotalFields: 16 columns

### Analysis Tasks
#### Use pivot tables and calculated columns where necessary to answer the following:
1. What is the average discount percentage by product category?
2. How many products are listed under each category?
3. What is the total number of reviews per category?
4. Which products have the highest average ratings?
5. What is the average actual price vs the discounted price by category?
6. Which products have the highest number of reviews?
7. How many products have a discount of 50% or more?
8. What is the distribution of product ratings (e.g., how many products are rated 3.0, 4.0, etc.)?
9. What is the total potential revenue (actual_price × rating_count) by category?
10. What is the number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)?
11. How does the rating relate to the level of discount?
12. How many products have fewer than 1,000 reviews?
13. Which categories have products with the highest discounts?
14. Identify the top 5 products in terms of rating and number of reviews combined.

### Final Task: Dashboard Creation
#### Using your cleaned dataset and pivot outputs, build an Excel dashboard.
##### Unleash your Creativity.

## HEADER.
![Heading](https://github.com/user-attachments/assets/38b0a7b4-4e05-41d6-b4c0-3b164e8ac5bd)

## LOGO.
![Logo](https://github.com/user-attachments/assets/b1e2174b-e8c8-4efd-aa45-3d4375ee1b07)

## COLOR.
![Colour](https://github.com/user-attachments/assets/e4b98e5d-388e-4509-bddb-4286d80171ac)

## INFO.
![HOME SCROLL](https://github.com/user-attachments/assets/47218368-031a-4611-9c13-653cc62d0752)


# Step-By-Step Guide 
##Using MS Excel;

## TABLES.
![Tables](https://github.com/user-attachments/assets/34b88f60-7f43-4dda-bee6-59b8eb5b8a25)

## CARDS.
![Uplo![CARDS (2)](https://github.com/user-attachments/assets/fa573c7f-4014-48ba-9b9a-30be7ba8ff86)
ading CARDS.png…]()

## SLICERS.
![Slicer's](https://github.com/user-attachments/assets/83d8e940-f702-4d0d-9f91-8f072ab89756)

## PIVOT TABLES.
![PIVOT TABLES AND SLICERS](https://github.com/user-attachments/assets/936ab0c7-2b98-43ee-b0b9-88a3dc3d4908)


### Step 1: Data Cleaning & Preparation

1. Open your dataset in Excel.
2. Check for missing values:
   - Use `Filter` to find blanks in key columns like `Product Name`, `Category`, `Price`, `Rating`, etc.
   - Remove or fill missing values as appropriate.

3. Create calculated columns**:
   - Discount% %:
     ```excel
     =IF(Original_Price=0, 0, (Original_Price - Discounted_Price)/Original_Price)
     ```
   - Potential Revenue:
     ```excel
     =Discounted_Price * Rating_Count
     ```
--- 

### Step 2: Pivot Table Analysis

Go to Insert > Pivot Table and use the following setups:

### 1. Average Discount% % by Category.
#### (Cards).
- Rows: `Category`
- Values: `Discount% %` (set to Average)

### 2. Product Count per Category.
- Rows: `Category`
- Values: `Product Name` (set to Count)
![Product Count By Category](https://github.com/user-attachments/assets/5a1c604d-b2b4-4a90-9c9d-991a556d3335)


### 3. Total Reviews per Category.
#### (Cards).
- Rows: `Category`
- Values: `Rating_Count` (set to Sum)

### 4. Highest Average Ratings.
#### (Cards).
- Sort the dataset by `Rating` in descending order
- Use `Filter` to find top-rated products

### 5. Average Actual vs Discounted Price by Category.
#### (Tables).
- Rows: `Category`
- Values: `Original_Price` (Average), `Discounted_Price` (Average)
![Actual Price vs Discounted Price By Category](https://github.com/user-attachments/assets/86d93a38-6328-4f72-aeb5-7ed1fae16c84)


### 6. Products with the Highest Number of Reviews.
#### (Cards).
- Sort the dataset by `Rating_Count` descending

### 7. Products with ≥50% Discount
#### (Calculated Columns).
- Use a filter or formula:
  ```excel
  =IF([@[Discount %]]>=0.5, "Yes", "No")
  ```
- Count the "Yes" entries

### 8. Rating Distribution.
- Create a pivot:
  - Rows: `Rating`
  - Values: `Product Name` (Count)
![Rating Distribution](https://github.com/user-attachments/assets/e606cea3-986f-4677-ac8f-9a7295d8a5b0)


### 9. Total Potential Revenue by Category.
- Rows: `Category`
- Values: `Potential Revenue` (Sum)

### 10. Price Range Buckets
#### (Calculated Columns).
- Add a column:
  ```excel
  =IF(Discounted_Price<200,"<₹200",IF(Discounted_Price<=500,"₹200–₹500",">₹500"))
  ```
- Use pivot to count products per bucket

### 11. Rating vs Discount.
#### (Calculated Columns).
- Insert a scatter plot:
  - X-axis: `Discount%`
  - Y-axis: `Rating`
![Rating vs Discount](https://github.com/user-attachments/assets/546acdb4-8a80-489e-8f0a-79c845044a6e)


### 12. Products with <1,000 Reviews.
#### (Calculated Columns).
- Use a filter or formula:
  ```excel
  =IF(Rating_Count<1000, "Yes", "No")
  ```
- Count the "Yes" entries

### 13. Categories with Highest Discounts.
- Use pivot:
  - Rows: `Category`
  - Values: `Discount%` (Average)
  - Sort descending

### 14. Top 5 Products by Rating × Review Count.
#### (Calculated Columns).
- Add a column:
  ```excel
  =Rating * Rating_Count
  ```
- Sort descending and pick the top 5
![TOP (5) PRODUCTS (in terms of Rating x Review Count)](https://github.com/user-attachments/assets/f83fc7e8-aa58-439c-be4b-e054529eb486)


---

## Step 3: Dashboard Creation.

1. I created a new sheet called `Dashboard`
2. Use:
   - Pivot charts (bar, column, pie, scatter)
   - Slicers for Category, Price Range, Rating
   - KPI Cards using large text boxes for:
     - Total Revenue
     - Average Rating
     - Number of High Discount Products
3. Design Tips:
   - Use consistent colors
   - Group visuals logically (e.g., pricing, reviews, ratings)
   - Add titles and labels for clarity
![DASHBOARD](https://github.com/user-attachments/assets/855316d2-3324-40f3-8cde-b6a2685c83bb)

---

## Final Touches.

- Add interactivity with slicers
- Use conditional formatting to highlight key metrics
- I saved the file as `.xlsx`.

---
✨
