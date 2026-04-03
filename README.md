*🎮 Video Game Recommender — PySpark ALS on AWS EMR**

A collaborative filtering recommendation system built with PySpark MLlib and deployed on AWS EMR. Trained on 4.6 million Amazon Video Games reviews to generate personalized Top-N game recommendations for users.

**📌 Overview**

With millions of video games available across platforms, discovering new games that match a user's taste is a real challenge. This project tackles that using Alternating Least Squares (ALS) — a matrix factorization technique that learns latent preferences from historical user-item ratings.

The full pipeline runs on AWS EMR (Elastic MapReduce), reading data from S3, processing it with PySpark, and writing recommendations back to S3.

**🗂️ Dataset**

Source: Amazon Product Reviews — Video Games category (JSONL format)

Storage: AWS S3

Raw size: 4,624,615 reviews

After cleaning: 3,982,807 rows (filtered to verified purchases)

After cold-start filter: 706,564 rows

Unique users: 90,846

Unique items: 59,042

Rating range: 1.0 – 5.0 (mean: ~4.1)

**🤖 Model — ALS (Alternating Least Squares)**

ALS is a matrix factorization algorithm for collaborative filtering. It decomposes the user-item ratings matrix into two lower-rank matrices (user factors and item factors), learning latent preferences from observed ratings.

**🚀 How to Run**
Prerequisites

  1. AWS account with EMR and S3 access
  2. An S3 bucket containing Video_Games.jsonl

Steps

  1. Launch an EMR cluster with JupyterHub or EMR Studio (PySpark kernel)
  2. Upload FinalProject.ipynb to your EMR Studio workspace
  3. Update S3 paths in the notebook:
     S3_INPUT_PATH = "s3://YOUR-BUCKET-NAME/Video_Games.jsonl"
     S3_OUTPUT_PATH = "s3://YOUR-BUCKET-NAME/output/"
  5. Run all cells top to bottom

Output

Results are saved to S3:

1. output/user_recommendations/ — Top-10 game recs per user (Parquet)
2. output/test_predictions/ — Predicted ratings on test set (Parquet)
