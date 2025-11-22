# 🎬 Movie Recommendation System using Stacked Autoencoders

This repository contains a **Movie Recommendation System** implemented with a **Stacked Autoencoder (SAE)**.  
The model learns from user–movie ratings and predicts unseen ratings, allowing us to recommend movies a user is likely to enjoy.

---

## 📌 Project Overview

Traditional recommendation systems use:
- **User-based** or **item-based** collaborative filtering  
- Similarity measures like cosine similarity or Pearson correlation  

In this project, we use a **neural network–based approach**:
- A **Stacked Autoencoder** learns a compressed representation of user preferences.
- The model reconstructs the full rating vector, including missing ratings.
- The reconstructed ratings are used to recommend top movies for each user.

---

## 🧱 Main Steps in the Notebook

### 1️⃣ Importing Libraries
- Load all required Python packages:
  - `numpy`
  - `pandas`
  - `torch` / `tensorflow` (depending on your implementation)
  - Other utility libraries for preprocessing and evaluation

### 2️⃣ Data Preprocessing
- Load user–movie ratings dataset  
- Convert it into a **user–item matrix**  
- Handle:
  - Missing ratings
  - Train/test split (e.g., different users or different ratings)

### 3️⃣ Architecture of Neural Network (SAE)
Typical architecture:
```text
Input Layer:    number_of_movies
       ↓
Hidden Layer 1
       ↓
Hidden Layer 2 (bottleneck / latent features)
       ↓
Hidden Layer 3
       ↓
Output Layer:   number_of_movies (reconstructed ratings)
