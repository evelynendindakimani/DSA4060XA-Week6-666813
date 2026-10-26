# DSA 4060XA — Week 6: Guided Evaluation Lab

* **Student Name:** Evelyne Kimani
* **Student ID:** 666813
* **Course:** DSA 4060XA

---

## 1. Lab Objective
The objective of this lab is to implement, evaluate, and compare three distinct recommender systems,Popularity Baseline, Content-Based Filtering, and Item-Based Collaborative Filtering (CF)moving beyond traditional rating prediction accuracy (MAE/RMSE) to evaluate ranking quality (Precision@K, Recall@K, NDCG@K) and beyond-accuracy metrics (Catalogue Coverage, Novelty, and Diversity).

---

## 2. Models Compared
1. **Popularity Baseline:** Recommends globally highest-rated and most frequent movies to all users without personalization.
2. **Content-Based Recommender:** Recommends movies matching the genre feature profiles of items the user has historically liked.
3. **Item-Based Collaborative Filtering (CF):** Recommends items based on user-item interaction patterns and item-item similarity derived from historical ratings.

---

## 3. Evaluation Findings

### Rating Prediction (MAE & RMSE)
* **Best Model for Rating Prediction:** Item-Based CF = It has the highest MAE and RMSE
* **Finding:** While advanced models generally reduce error compared to the naive popularity baseline, rating prediction accuracy alone does not guarantee a useful Top-N recommendation list.

### Ranking Quality (Precision@3, Recall@3, NDCG@3)
* **Best Model for Ranking:** Item-Based CF demonstrated stronger capability in placing relevant items ($\ge 4$ stars) near the top of the recommendation list compared to the static popularity list.

### Beyond-Accuracy Findings (Coverage, Novelty, Diversity)
* **Catalogue Coverage:** The Popularity Baseline suffers from low coverage because it locks recommendations into a small set of blockbuster titles. Item-Based CF and Content-Based models expose a much wider fraction of the movie catalogue.
* **Novelty:** Content-Based and CF models scored significantly higher in novelty, successfully surfacing niche or less mainstream films compared to the baseline.
* **Diversity:** Genre cosine-similarity evaluations showed that personalized models offer more varied internal list items, preventing redundancy within a user's Top-3 list.

---

## 4. Final Recommended Model & Business Scenario
**Scenario:** A streaming service looking to balance user discovery of relevant movies while preventing the same popular blockbusters from dominating every recommendation list.

* **Recommended Model:** **Item-Based Collaborative Filtering (or Content-Based)**
* **Key Driving Metrics:** Precision@3, Catalogue Coverage, and Novelty/Diversity.
* **Trade-off Accepted:** Accepting a slight reduction in absolute global popularity matching in exchange for significantly higher content discovery, user personalization, and broader catalogue exposure.

---

## 5. Evaluation Limitations
1. **Cold-Start Problem:** The models struggle to provide personalized or accurate recommendations for new users or new movies with little to no historical interaction data.
2. **Subjective Relevance Threshold:** Defining relevance strictly as a rating of $\ge 4$ is binary and arbitrary; it fails to capture nuanced user preferences or degrees of liking.
3. **Data Sparsity:** Matrix sparsity in the user-item rating matrix can introduce noise into item-item similarity calculations, occasionally affecting recommendation stability.

---

## Repository Structure
```text
DSA4060XA-Week6-666813/
├── DSA4060XA_Week6_Guided_Evaluation_Lab.ipynb
├── DSA4060_Week6_Movies.csv
├── DSA4060_Week6_Ratings.csv
└── README.md
