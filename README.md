# Capstone-Project-Cart-Abandonment

## Summary of Business Problem and Project Objective

Swire Coca-Cola currently faces a problem with cart abandonment on its new MyCoke360 platform. The goal of this project is to identify what behaviors or sequences of events lead to cart abandonment. Once these behavioral loops are identified, we can make recommendations to Swire Coca-Cola about potential interventions to prevent cart abandonment and loss of revenue.  

A cart was considered abandoned if an item was added to the cart and a purchase did not occur before the end of the purchase window. Our goal was to identify the issues that customers were encountering; estimating the amount of lost revenue due to abandonment was considered outside the scope of this project.

---

## Solution to the Problem

Our group used data from google_analytics.csv, orders.csv, visit_plan.csv, customer.csv, cutoff_times.csv, operating_hours.csv, and material.csv to create a combined table. Using this combined dataset, we identified 50,910 purchase windows and found that 14.8% of these windows resulted in abandoned carts.  

Using a comparison of means to examine how frequently different behaviors occurred within a purchase window, we found that events such as viewing items and searching for items occurred more frequently in abandoned carts than in non-abandoned carts.  

Association rule mining provided deeper insight, showing that customers in abandoned carts often became stuck in what we called “friction loops” of updating carts, adding items to carts, and viewing carts. This suggests that customers may be having difficulty finding the right SKU, the correct pack size, or the appropriate product type.

---

## My Contribution

I completed much of the data preparation, including merging datasets and adjusting timestamps. I also normalized the event_name column so that we could compare purchase windows with each other.  

For the analysis portion, I conducted the basic descriptive analytics across different products, categories, pack sizes, and flavors. I also built the final clustering model that was used in our notebook and presentation.

---

## Business Value

We recommended that Swire Coca-Cola incorporate a feature into the checkout process to assist customers when they enter these friction loops. This could include a live customer service representative or an artificial intelligence–based chat feature to help customers find what they are looking for.

---

## Difficulties Encountered

There were several limitations to the data. For example, we did not have any data from the period prior to the implementation of the MyCoke360 platform. This would have allowed us not only to compare abandonment rates before and after the platform launch, but also to perform a causal analysis. Approximately 23,000 rows of data were missing key information.  

Creating the purchase windows was a considerable challenge. We had to adjust timestamps for different events and purchase cutoff times based on the locations of the regional sales offices. Additionally, there were no unique purchase or transaction identification numbers, so we used a combination of timestamps and customer identifiers to group items that were purchased together.  

We initially tested several modeling approaches, including random forest, gradient boosting, and logistic regression. However, these models did not provide the type of insight we needed. As a result, midway through the project we shifted our approach to a more descriptive and differential analysis.

---

## What I Learned

This was my first time working with timestamps and other date-specific data at a large scale. Due to the large volume of data, I used the data.table format for more efficient processing, but as a result, much of my prior experience using tidy syntax was not as applicable. Additionally, working through the different types of date objects and formats was a new experience for me.  

I also experimented with more clustering methods than I had in the past. Many of the more common methods, such as k-means or kernel-based approaches, did not perform well with this data. This project required me to use PCA in conjunction with the DBSCAN clustering method in order to obtain identifiable clusters.
