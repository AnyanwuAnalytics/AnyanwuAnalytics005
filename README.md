ElectroMetric Sales & Customer Behavior Dashboard, 2023–2024
<img width="617" height="299" alt="Screenshot 2026-11-11 182449" src="https://github.com/user-attachments/assets/20bfdf27-ed53-4113-aab7-4b7d5b49fde9" />
Understanding how customers buy, pay, and engage across the ElectroMetric sales ecosystem

Introduction

I went in looking for the usual things. Which product sells best? Do loyalty members spend more? Do younger shoppers buy more add-ons? I had a guess for each one. Ideally, we would all agree with my guesses, but every dataset is different, and this one had its own story: 1 in every 3 orders was cancelled.

That one number changed how I read everything else in this project, so let me take you through it.

This project is an Excel dashboard built on an electronic sales dataset. Here is what is in it:

20,000 rows, and each row is one order
12,136 customers, and 5,499 of them ordered more than once
16 columns in the raw file, which became 19 after I added three of my own
Orders placed between 24 September 2023 and 23 September 2024
5 products: Smartphone, Tablet, Smartwatch, Laptop and Headphones
5 payment methods and 5 shipping types
$64.85M of orders placed, $43.47M of Net Revenue kept, and $21.38M lost to cancellations
Yes, you read that right. Out of $64.85M that customers tried to spend, $21.38M never turned into money.

So, the question I kept asking was not “which product wins?” but “where is the money going, and why?” Let’s find out.

Data Story

The data tells the story of one electronics store over one year. Each order shows who bought (age, gender, loyalty status), what they bought (product, SKU, unit price, quantity), how they paid, how they chose to have it shipped, whether they added an extra item, whether the order was completed or cancelled, and the rating they gave.

On the surface it looks like a normal, healthy year. Revenue stepped up in January 2024 and stayed steady for months after that. But underneath, 6,568 of the 20,000 orders were cancelled. That is 32.84%, and it is worth $21.38M. If none of them had been cancelled, revenue would have been about 49% higher. That is the story I kept coming back to, and everything else in the analysis was read with it in mind.

Data Tool and Source

Tool: Microsoft Excel. I used PivotTables and PivotCharts for the analysis.

Source: [https://www.kaggle.com/datasets/abdullehkamel/electronic-sales-data-analysis-sep23-sep24]

Cleaning Process

Before building anything, I observed the dataset and cleaned what needed cleaning:

Kept the raw data safe. I left the original in the Before sheet and worked on a copy.
Fixed inconsistent spelling. Payment Method had “Paypal” and “PayPal” as two different labels. I made them one.
Turned text into numbers. Actual Revenue had zeros stored as text for cancelled orders. I converted them to real numbers so totals and averages work properly.
Made the SKU codes clean. The raw file had 10 SKU codes for only 5 products, because some products had two code styles. I mapped them to one clean code per product (SMP234 for Smartphone, TBL345 for Tablet, LTP123 for Laptop, SWT567 for Smartwatch and HDP456 for Headphones). Three rows where the SKU did not match the product type were corrected too. I kept every original unit price, so no sales value was changed.
Simplified add-ons. The raw column listed long item names. I changed it to Yes or No, because my questions are about whether people buy add-ons, not which one. The details are still in the Before sheet.
Added three columns. Month-Year for the monthly trend, Order Total (Total Price plus Add-on Total), and Actual Revenue (the Order Total if the order was Completed, and 0 if it was Cancelled).
Checked the basics. No blank cells in the data, and the calculated columns match their formulas.

Columns Within the Data

Customer ID: the customer who placed the order
Age: the customer’s age, from 18 to 80
Gender: Male or Female
Loyalty Member: Yes or No for that order
Product Type: Smartphone, Tablet, Smartwatch, Laptop or Headphones
SKU: the clean product code
Rating: the customer’s score, from 1 to 5
Order Status: Completed or Cancelled
Payment Method: Credit Card, PayPal, Bank Transfer, Cash or Debit Card
Total Price: Unit Price times Quantity
Unit Price: the price of one item
Quantity: the number of items in the order
Purchase Date: the day of the order
Month-Year (added): the month of the order, used for the trend
Shipping Type: Standard, Expedited, Same Day, Overnight or Express
Add-ons Purchased: Yes or No
Add-on Total: the money spent on add-ons
Order Total (added): Total Price plus Add-on Total
Actual Revenue (added): the money actually earned, which is 0 for cancelled orders

Pre Analysis Board

Before building any chart, I planned my work.

Data Splitting

Independent variables (what I group by): Age, Gender, Loyalty Member, Product Type, SKU, Unit Price, Quantity, Payment Method, Shipping Type and Purchase Date.

Dependent variables (what I measure): Order Status, Rating, Add-ons Purchased, Add-on Total, Total Price, Order Total and Actual Revenue.

Customer ID is just an identifier, so I only used it to count.

Industry Type

This industry belongs to the Consumer Electronics E-commerce industry. The store sells high-value devices like smartphones and laptops alongside lower-priced headphones, and every sale depends on a smooth chain from payment to delivery.

Stakeholders

Sales & Marketing need to know which customers and products bring the money, and whether loyalty and add-ons are worth pushing.
Operations/Logistics focus on shipping types and the high number of cancelled orders.
Finance care about Net Revenue against the order value lost to cancellations.
Inventory & Merchandising need to know which products sell and rate well, so stock is placed where it earns.

What Success Means

Success in this industry is about turning the orders customers place into orders that are actually delivered. For this data, that means bringing down the 32.84% cancellation rate, because $21.38M of order value never became revenue. A good year also means steady monthly net revenue, products customers rate well, add-ons that raise the value of each order, and the right stock held for the shipping speeds customers choose.


Potential Question

What is the total Net Revenue?
How much was lost to cancellations, and what is the cancellation rate?
What is a typical completed order worth?
Which product has the highest rating?
Which age group spends the most on add-ons?
What share of completed orders comes from loyalty members?
Do loyalty members cancel less?
Which payment method is used most?
Which product earns the most revenue?
How do completed orders split across shipping types?
Which product sells the most items?
How did revenue move across the year?

In Analysis

Here is what I found. A cancelled order never turns into money, so the charts show completed orders (13,432 of the 20,000). I tracked the cancelled ones separately in the Lost to Cancellation card.

The Key Numbers

Observation: 20,000 orders brought in $43.47M of Net Revenue. 6,568 orders (32.84%) were cancelled, worth $21.38M. The average completed order is worth $3,236.
Insight: the cancelled value equals 33% of everything customers tried to buy. That makes it the biggest lever in this data.

Product Ratings by Category
<img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/00fa0b7a-e614-435f-8381-dbd0abf4d3f2" />


Observation: Smartphones have the highest average rating at 3.33 out of 5. Tablets are at 3.03, Smartwatches 3.00, Headphones 2.99 and Laptops 2.97.
Insight: only Smartphones really stand out. The other four are tied around 3.0. The average also hides something. 40% of Smartphone ratings are 5 stars, but 47% are 1 or 2 stars. Headphones show the same split, with 20% five-star and 41% one or two stars. Smartphone and Headphone customers are either very happy or unhappy, and the data does not say why.

2. Add-on Spending by Age Group

<img width="752" height="452" alt="image" src="https://github.com/user-attachments/assets/af75651e-f306-436f-b639-5cdc8dd01f18" />


Observation: the average add-on per order runs from $60.48 (ages 68–77) to $64.26 (ages 28–37), against an overall average of $62.21.
Insight: I expected young shoppers to spend more on extras. They don’t. Across the full age groups the gap is only $3.78, about 6%. The 78–87 bar looks highest, but it only covers ages 78 to 80, with 624 completed orders against about 2,100 to 2,200 in the other groups. Add-ons are also small money. 75.5% of completed orders include one, worth about $82 each, and together they make up just 1.9% of Net Revenue.

3. Loyalty Shares of Orders

<img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/e5bca2a3-48a8-4556-b95f-dfed72caf1e5" />


Observation: 21.7% of completed orders (2,920) came from loyalty members, and 78.3% (10,512) from non-members.
Insight: I expected members to spend more. They don’t. Their average order is $3,179 against $3,252, and they cancel at the same rate (32.8% against 32.9%). The chart counts orders, not people, because 2,270 customers show up as both members and non-members at different times.

4. Top Payment Method

<img width="752" height="452" alt="image" src="https://github.com/user-attachments/assets/027ef7e7-c4ef-4933-aaed-8405a2a44fd4" />


Observation: Credit Card (29.0%) and PayPal (28.8%) lead, followed by Bank Transfer (16.8%), Cash (12.9%) and Debit Card (12.5%).
Insight: Credit Card and PayPal are practically tied, only 36 orders apart, and together they carry 57.8% of completed orders. Bank Transfer is used for the biggest orders, with an average of $3,824 against $2,586 for Cash. Cancellation is about the same for every method (30.7% for Cash up to 33.6% for Credit Card), so no payment method is causing it.

5. Net Revenue by Product

<img width="752" height="452" alt="image" src="https://github.com/user-attachments/assets/9c3f3f24-c865-4ebb-8d81-63a5c1537243" />


Observation: Smartphones earned $14.63M (33.7%), Smartwatches $9.56M (22.0%), Laptops $8.54M (19.6%), Tablets $7.89M (18.2%) and Headphones $2.85M (6.6%).
Insight: revenue follows price as much as popularity. Smartwatches earn 22.0% of revenue from 19.6% of orders because their average order is $3,626. Tablets earn 18.2% from 20.4% of orders because theirs is $2,876.

6. Shipping Type Shares

<img width="751" height="451" alt="image" src="https://github.com/user-attachments/assets/9d26b6cc-6971-4384-8f06-5de0853a7589" />

Observation: Standard carries 33.8% of order value. Expedited carries 19.8%, Same Day 19.5%, Overnight 13.8% and Express 13.2%.
Insight: Standard is twice as popular as any other type. Expedited and Same Day carry more value than their share of orders because they hold pricier items ($681 to $692 per unit, against $468 to $482 for Overnight and Express), not because people buy more items. Among the biggest 25% of orders, the shipping mix is almost the same as for everyone else, so big spenders don’t specifically choose fast delivery.

7. Total Items Sold per Category

<img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/303476ae-809d-41b6-ac62-bfbf2f5f90da" />


Observation: completed orders moved 73,650 items. Smartphones sold 21,947, Tablets 15,041, Laptops 14,623, Smartwatches 14,474 and Headphones 7,565.
Insight: Smartphones lead on volume, and Headphones sell about a third as many. Tablets, Laptops and Smartwatches are within 4% of each other. Counting cancelled orders would give 109,711 items, so about a third of the items customers ordered never shipped.

8. Monthly Sales Trend

<img width="828" height="550" alt="image" src="https://github.com/user-attachments/assets/b94f2f30-2b3b-44e3-a821-2337d4ae2c7f" />


Observation: net revenue was $1.6M in October 2023, $1.4M in November and $1.3M in December. It jumped to $4.6M in January 2024, then stayed between $4.0M and $4.6M until August.
Insight: the story is a step up in January 2024, not a crash. Revenue was 3.5 times December’s. Orders per day rose from about 27 to about 65, and the average completed order grew from about $2,580 to about $3,330. The data doesn’t say why. September 2023 and September 2024 are partial months (7 and 23 days), so those dips are not real drops.

Post Analysis

Once the dashboard was done, I stepped back and looked at all the charts together. Here is what stood out.

Observations

Cancellations are the same everywhere. The overall rate is 32.84%. By product it runs from 32.3% to 33.1%, by payment method from 30.7% to 33.6%, by shipping type from 32.2% to 33.8%, and by age group from 31.9% to 33.4%. Members and non-members cancel at almost the same rate.
Smartphones lead on what matters. They have the most revenue (33.7%), the most items sold (29.8%) and the best rating (3.33), although their ratings are split.
Price drives revenue more than popularity. Smartphones and Smartwatches earn more per order than Tablets, Laptops and Headphones.
Several things I expected to matter don’t. Age barely changes add-on spending, loyalty doesn’t change order size, and big orders don’t favor fast shipping.
Revenue stepped up once in January 2024 and then held steady at about $4.4M a month.

Insights

Fixing cancellations is the biggest opportunity. Because the rate is about the same in every group, I don’t think one product, payment method or shipping type is to blame. The cause is more likely something every order goes through, like checkout, stock confirmation or waiting time for delivery. The data has no cancellation reasons, so I can’t say which. As a rough estimate, every 1 point cut in the cancellation rate is worth about $650,000 of Net Revenue.
Loyalty and add-ons are small levers. Members behave like everyone else, and add-ons are only 1.9% of Net Revenue.
The Smartphone and Headphone rating split deserves a closer look, because nearly half of their buyers gave 1 or 2 stars.
A word of caution about this data. It covers one year, it has no cancellation reasons, and many differences are tiny. For example, there are about 5.5 items in every order no matter the product. I treated tiny differences as ties, not findings.

Overall Recommendations

Operations/Logistics

Record a cancellation reason on every cancelled order (changed mind, payment failed, out of stock, delivery too slow), and review the top reason after three months.
Walk through the order process from checkout to dispatch and look for where orders drop out. A 10 point drop in cancellations would mean about 2,000 more completed orders, around $6.5M.
Keep Standard shipping as the default. It is the most used type and has the lowest cancellation rate (32.2%).

Sales & Marketing

Offer add-ons to all ages, not just one age group. It is a bonus, since add-ons are only 1.9% of revenue.
Review the loyalty program. Members cancel and spend like non-members, so add a perk that matters and check after three months whether their orders get bigger or cancel less.
Find out what changed in January 2024 (a campaign, a price change, a new channel) and repeat it.

Finance

Report Net Revenue, cancelled value and the cancellation rate together every month, and plan from the January to August level of about $4.4M a month.

Inventory & Merchandising

Keep Smartphones as the stock priority, then Smartwatches. Together they earn 55.7% of Net Revenue.
Read the reviews and returns for Smartphones and Headphones to find out why so many buyers give 1 or 2 stars. Do this before any pricing or bundling changes.

Conclusion

The store had a strong 2024. Revenue stepped up in January, to 3.5 times what it was in December, and it held steady at about $4.4M a month through August. Smartphones led almost everywhere. They earned 33.7% of Net Revenue, sold the most items and had the best rating. Smartwatches came second on revenue because their orders are worth more, and Headphones earned the least at 6.6%. Credit Card and PayPal were almost tied as the favourite ways to pay, and Standard shipping was the most used by far, with about twice the orders of any other type. But the number that stayed with me was this one: 32.84% of all orders were cancelled.





