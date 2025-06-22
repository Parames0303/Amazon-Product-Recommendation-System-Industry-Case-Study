# Amazon-Product-Recommendation-System-Industry-Case-Study
Amazon Product Recommendation System —Industry Case Study
# 🛍️ Amazon Product Recommendation System — Industry Case Study

This project builds and evaluates a **hybrid recommendation engine** for an e-commerce platform using both **content-based** and **collaborative filtering** techniques.

---

## 📌 Problem Statement

> Build a smart recommendation system using product metadata and user behavior data to personalize shopping experiences for Amazon users.

---

## 🗃️ Dataset Summary

| Feature                    | Count / Range                          |
|---------------------------|----------------------------------------|
| Unique Users              | ~X users                               |
| Unique Products           | ~Y products                            |
| Total Ratings/Reviews     | ~Z reviews                             |
| Top 5 Product Categories  | Electronics, Clothing, Mobiles, Footwear, Accessories |
| Price Range               | ₹50 – ₹200,000                         |
| Discount % Range          | 0% – 95%                               |

---

## 🔧 Tools & Libraries

- **Python**, **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn**
- **Scikit-learn**, **TF-IDF**
- **Cosine Similarity**, **Collaborative Filtering**

---

## 🧼 Section A: Data Understanding & Cleaning

- Cleaned and converted:
  - `actual_price`, `discounted_price`, `discount_percentage`
- Normalized `rating` and `rating_count`
- Created derived fields:
  - `price_difference`, `value_for_money_score`, `weighted_rating`
- Split hierarchical `category` into 3 levels
- Handled missing values and dropped duplicates

---

## 📊 Section B: Exploratory Data Analysis (EDA)

Visualized:
- Most reviewed products
- Top categories by product count
- Average rating per category
- Discount vs actual price correlation

🧠 **Insights:**
1. Some high-rated products have very few reviews (opportunity for exposure)
2. Heavy discounts correlate moderately with higher review counts
3. Mobile phones dominate both in volume and rating count

---

## 🧠 Section C: Content-Based Filtering

- Vectorized `product_name + about_product` using **TF-IDF**
- Calculated cosine similarity to recommend similar products
- Enhanced with category and price-weighted similarity
- Recommended items even for new/unrated products

---

## 🤝 Section D: Collaborative Filtering

- Created a **User–Item Matrix** with ratings
- Implemented **User-User Collaborative Filtering** using cosine similarity
- Recommended top N unseen products per user

---

## 🔀 Section E: Hybrid Recommender System

> Combines both collaborative and content-based scores:

```python
hybrid_score = 0.6 * CF_score + 0.4 * Content_score

    Handles cold-start scenarios (new product or new user)

    Balances relevance and personalization

    Evaluated for both sparse and dense user profiles

🚀 Section F: Business Strategy & Deployment
✅ Best Model for:

    New Users → Content-Based

    Returning Users → Collaborative Filtering

🔧 Real-World Deployment Plan:

| Layer            | Technology                           |
| ---------------- | ------------------------------------ |
| Model Serving    | Flask / FastAPI + Gunicorn           |
| Batch Pipeline   | Airflow / AWS Glue                   |
| Real-Time Stream | Apache Kafka / Amazon Kinesis        |
| Deployment       | Docker + Kubernetes                  |
| Storage Layer    | Redis (cache), PostgreSQL (fallback) |

📈 KPIs to Monitor:

    Click-Through Rate (CTR)

    Conversion Rate

    Add-to-Cart Rate

    Precision / Recall @ K

    Revenue per Session

    Diversity / Novelty Score

📁 Project Structure
amazon-product-recommender/

├── Amazon_recommedation_sysem.ipynb  # Annotated Jupyter Notebook
├── data/
│   └── amazon.csv               # Dataset

└── README.md                    # This file

💡 Sample Usage

recommend_similar_products("Samsung Galaxy M13", top_n=5)
recommend_cf("U1004531")
hybrid_recommend("U1004531", "galaxy", top_n=5)

👨‍💻 Author

Parameswaran P
Public Cloud Architect | AI/ML Enthusiast
📍 Tamil Nadu, India
