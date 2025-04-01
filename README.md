# Fraud-Detection
Fraud Pattern Discovery via Anomaly Detection
# 🕵️‍♀️ Fraud Detection with Unsupervised Learning

This project applies unsupervised learning techniques to detect potential fraud patterns using anonymized financial transaction datasets from the [FiFAR](https://www.fraud-detection-handbook.de/) research study. The analysis explores three dataset variants (Variant II, Base, and Variant IV), each designed with unique fraud distribution profiles.

---

## 🧠 Objective
The goal is to explore whether unsupervised learning models — specifically clustering — can reveal underlying patterns in transaction behavior that may indicate fraudulent activity, without using labeled fraud data during training.

---

## 🗃️ Datasets Overview

| Variant     | Description                                         |
|-------------|-----------------------------------------------------|
| Variant II  | Balanced sampling to expose rare fraud patterns     |
| Base        | Original distribution of transactions               |
| Variant IV  | Over-sampled fraud to emphasize risky behaviors     |

Each dataset includes ~1 million records and over 50 features related to:
- Customer demographics & activity
- Banking behavior
- Device metadata
- Transaction velocity & risk scores

---

## 🧪 Methods
- Preprocessing: scaling, one-hot encoding, cyclical month encoding
- Dimensionality Reduction: PCA (2D) for visualization
- Clustering Models: K-Means, DBSCAN, Gaussian Mixture Models (GMM)
- Model Evaluation: Silhouette Score, visual inspection, fraud distribution analysis
- Interpretation: Cluster-level fraud analysis and feature profiling

---

## 📌 Results Snapshot

| Variant     | Best Model | Top Fraud Cluster (%) | Silhouette Score |
|-------------|------------|------------------------|------------------|
| Variant II  | GMM        | Cluster 2 (2.25%)      | 0.0830           |
| Base        | GMM        | Cluster 2 (2.00%)      | 0.0794           |
| Variant IV  | GMM        | Cluster 1 (3.07%)      | 0.0748           |

> GMM consistently outperformed K-Means and DBSCAN in segmenting clusters with high fraud concentration.

---

## 📊 Tableau Visualizations
Interactive dashboards were created using a consolidated dataset combining all three variants:
- Fraud Rate by GMM Cluster
- Feature Distribution by Cluster & Variant
- Customer Risk Profiles

📎 [Explore the Dashboard](https://public.tableau.com/views/FraudDetectionClusterFeatureResults/ClusterExploration?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

---

## 📁 Repository Structure
```
fraud-detection-unsupervised/
├── data/
│   ├── raw/                         
│   └── processed/                   
├── notebooks/
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_pca.ipynb
│   ├── 03_clustering.ipynb
│   ├── 04_cluster_interpretation.ipynb
│   ├── ... (Base + Variant IV versions)
├── images/                         
├── fraud_clusters_tableau.csv      
└── README.md
```

---

## 📝 Key Takeaways
- Unsupervised learning can meaningfully segment fraud-prone behaviors
- GMM proved most effective at identifying soft fraud clusters
- Profiles such as low credit score + short sessions + foreign requests were common among risky clusters

---

## 🔮 Next Steps
- Deploy as a semi-supervised pipeline for real-time flagging
- Integrate behavioral features such as navigation patterns, IP/device frequency
- Explore autoencoders for anomaly detection

---

## 👩‍💻 Author
**Veronica Magdaleno**  
Data Scientist | AI Enthusiast | Problem Solver  
📫 [jobsearchvmagda@gmail.com](mailto:jobsearchvmagda@gmail.com)
