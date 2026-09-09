# Amazon Product Sales Analysis

This project analyzes Amazon product listings to understand which product and listing characteristics are associated with higher purchase activity.

The analysis looks at product categories, pricing, discounts, ratings, reviews, Best Seller status, coupons, sponsored listings, and other listing attributes.

## Business Questions

The analysis focuses on a few practical questions:

- Which product categories have higher purchase activity?
- Is there a relationship between ratings, reviews, and purchases?
- How do product price and discount levels relate to demand?
- Do Best Seller products show higher purchase activity?
- Is there a difference in purchases between products with and without coupons?
- How do sponsored and organic listings compare?
- What characteristics are common among high-demand products?

## Dataset

The dataset contains **42,675 Amazon product listings** with information about:

- Product title and category
- Product rating
- Number of reviews
- Purchases in the last month
- Original and discounted price
- Discount percentage
- Best Seller status
- Sponsored status
- Coupon availability
- Buy Box availability
- Delivery information
- Sustainability tags

The dataset is stored in the `data/` folder.

## Analysis

The notebook covers:

- Data cleaning and quality checks
- Missing-value analysis
- Duplicate checks
- Distribution of ratings, prices, discounts, reviews, and purchases
- Category-level analysis
- Price and discount analysis
- Relationship between reviews, ratings, and purchases
- Best Seller comparison
- Coupon analysis
- Sponsored vs. organic listing analysis
- High-demand product analysis
- Statistical testing using the Mann–Whitney U test
- Correlation analysis using log-transformed purchase data

## Key Findings

### Product Categories

**Power & Batteries** had the strongest purchase activity among the categories analyzed, with a median of around **1,000 purchases in the last month**.

**Wearables** followed with a median of around **800 purchases**.

Some larger categories, such as Phones and Laptops, had lower median purchase activity despite having many more listings.

### Reviews and Purchases

Products with more reviews generally showed higher purchase activity.

The correlation between log-transformed reviews and log-transformed purchases was approximately **0.49**, making reviews one of the stronger relationships observed in the dataset.

### Ratings

Higher-rated products tended to have higher purchase activity.

The correlation between rating and log-transformed purchases was approximately **0.27**.

High-demand products had a median rating of **4.7**, compared with **4.5** for the remaining products.

### Price

Lower-priced products generally had higher purchase activity.

When products were divided into four price groups based on discounted price:

| Price Segment | Median Purchases |
|---|---:|
| Low Price | 500 |
| Mid-Low Price | 200 |
| Mid-High Price | 100 |
| High Price | 50 |

This suggests that price is an important factor associated with purchase activity in this dataset.

### Best Seller Products

Best Seller products showed substantially higher purchase activity than other listings.

The median log-transformed purchase value was approximately:

- **Best Seller:** 8.70
- **Not Best Seller:** 5.30

A Mann–Whitney U test produced a p-value of approximately **1.12 × 10⁻¹⁰¹**, indicating a statistically significant difference between the two groups.

The result shows a strong association, but it does not establish that receiving a Best Seller badge causes higher sales.

### Coupons

Products with coupons had a median of approximately **700 purchases**, compared with **200 purchases** for products without coupons.

This suggests that coupon availability is associated with higher purchase activity.

### Sponsored Listings

Sponsored listings had higher observed purchase activity than organic listings.

The median purchases were approximately:

- **Sponsored:** 1,000
- **Organic:** 200

About **34% of sponsored listings** were classified as high-demand, compared with approximately **6% of organic listings**.

This should be interpreted as an association rather than a causal effect, since products may be sponsored because they are already performing well.

### High-Demand Products

High-demand products were defined as products at or above the **90th percentile of purchases in the last month**.

Compared with other products, high-demand products had:

- Median rating: **4.7 vs. 4.5**
- Median reviews: **5,045 vs. 288**
- Median discounted price: **$25.47 vs. $93.99**

Best Seller products were also more represented among high-demand products.

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

## Project Structure

```text
amazon-product-sales-analysis/
│
├── data/
│   └── amazon_products_sales_data_cleaned.csv
│
├── notebooks/
│   └── Amazon_Product_Sales_Analysis.ipynb
│
├── .gitattributes
└── .gitignore

