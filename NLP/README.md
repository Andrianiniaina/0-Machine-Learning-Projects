# 🛍️ THE NORTH FACE E-COMMERCE – PRODUCT CLUSTERING

## 🎯 Project Goals
**Group together similar products based on their textual descriptions using unsupervised learning and natural language processing.**

This project aims to enhance product navigation and recommendations on an e-commerce site by discovering natural groupings of products using clustering techniques.

---

## 📁 Data Description

- `sample-data.csv`: contains product descriptions and metadata

Key column:
- `description`: textual product description used for clustering

---

## 🔍 Project Workflow

### ✅ Text Preprocessing

- Cleaning HTML tags and special characters
- Tokenization with SpaCy
- Stop word removal
- Lemmatization

### ✅ Feature Extraction

- Encoding text using **TF-IDF (Term Frequency–Inverse Document Frequency)** via `TfidfVectorizer`

### ✅ Dimensionality Reduction

- Use of **Truncated SVD** to reduce TF-IDF dimensions for better clustering and visualization

### ✅ Clustering with DBSCAN

- Unsupervised clustering using **DBSCAN**
- Cosine distance used as the metric (adapted for text)
- Manual tuning of `eps` and `min_samples` to achieve ~10–20 clusters and minimize noise points

### ✅ Visualization

- Word clouds for each cluster
- 2D scatter plot of clusters

---

## 🛠️ Technologies & Libraries

- Python
- Pandas, NumPy
- SpaCy (NLP preprocessing)
- Scikit-learn (TF-IDF, DBSCAN, SVD)
- Matplotlib, WordCloud

---

## 📌 Recommendations

- Test other clustering techniques (KMeans, Agglomerative)
- Use embeddings (Word2Vec, BERT) for richer semantic representation
- Build an automated pipeline for new product clustering

---

## 👤 Author

Project by **Andriana**  
🔗 GitHub: [[https://github.com/tonprofil](https://github.com/Andrianiniaina/0-Machine-Learning-Projects)]([https://github.com/tonprofil](https://github.com/Andrianiniaina/0-Machine-Learning-Projects))

