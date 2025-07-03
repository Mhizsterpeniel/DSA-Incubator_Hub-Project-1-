# DSA-Project-Documentation-1-
This is another journey towards my Portfolio building while taking my Data Analysis class with Incubator Hub.
# DSA-Project-Documentation(1)
This is another journey towards my Portfolio building while taking my Data Analysis class with
Incubator Hub.

I have gained alot of data driven insights and knowledge regarding data analysis process and 
more related skills to data analysis ranging from aquiring skills on the great impact of various
tools in this field,
Tool's Like:
- MS Excel.
- SQL (Simple Query Language).
- Power BI.

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
## LOGO.
## COLOR.
## INFO.

# Step-By-Step Guide 
##Using MS Excel;

## TABLES.
## CARDS.
## SLICERS.
## PIVOT TABLES.

### Step 1: Data Cleaning & Preparation

1.Open your dataset in Excel.
2.Check for missing values:
   - Use `Filter` to find blanks in key columns like `Product Name`, `Category`, `Price`, `Rating`, etc.
   - Remove or fill missing values as appropriate.

3.Create calculated columns**:
   - Discount %:
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

### 1. Average Discount % by Category.
#### (Cards).
- Rows: `Category`
- Values: `Discount %` (set to Average)

### 2. Product Count per Category.
- Rows: `Category`
- Values: `Product Name` (set to Count)

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

### 6. Products with Highest Number of Reviews.
#### (Cards).
- Sort dataset by `Rating_Count` descending

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
  - X-axis: `Discount %`
  - Y-axis: `Rating`

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
  - Values: `Discount %` (Average)
  - Sort descending

### 14. Top 5 Products by Rating × Review Count.
#### (Calculated Columns).
- Add a column:
  ```excel
  =Rating * Rating_Count
  ```
- Sort descending and pick top 5

---

## Step 3: Dashboard Creation.

1. I Created a new sheet called `Dashboard`
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

---

## Final Touches.

- Add interactivity with slicers
- Use conditional formatting to highlight key metrics
- I saved the file as `.xlsx` and share with my team!

---
✨
