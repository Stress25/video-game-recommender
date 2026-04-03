**🎮 Video Game Recommender — PySpark ALS on AWS EMR**

A collaborative filtering recommendation system built with PySpark MLlib and deployed on AWS EMR. Trained on 4.6 million Amazon Video Games reviews to generate personalized Top-N game recommendations for users.

📌 Overview

With millions of video games available across platforms, discovering new games that match a user's taste is a real challenge. This project tackles that using Alternating Least Squares (ALS) — a matrix factorization technique that learns latent preferences from historical user-item ratings.

The full pipeline runs on AWS EMR (Elastic MapReduce), reading data from S3, processing it with PySpark, and writing recommendations back to S3.

🗂️ Dataset

Source: Amazon Product Reviews — Video Games category (JSONL format)
Storage: AWS S3
Raw size: 4,624,615 reviews
After cleaning: 3,982,807 rows (filtered to verified purchases)
After cold-start filter: 706,564 rows
Unique users: 90,846
Unique items: 59,042
Rating range: 1.0 – 5.0 (mean: ~4.1)

