# 🍽️ Semantic Clustering of Food Preparation Protocols using NLP Embeddings

## 📌 Overview
This project explores a novel approach to food processing classification by analyzing **cooking actions (protocols)** extracted from recipes. Instead of focusing only on ingredients (as done in traditional systems like NOVA), this work studies **how food is prepared** using NLP-based semantic embeddings and clustering techniques.

We apply multiple embedding models and hierarchical clustering to discover **latent semantic categories** of cooking actions such as cutting, mixing, heating, and transformation.

---

## 🎯 Objectives

- Extract cooking-action verbs (protocols) from recipe data  
- Create a **ground-truth semantic labeling** of protocols  
- Generate embeddings using multiple NLP models  
- Perform **hierarchical clustering**  
- Evaluate clustering quality using:
  - Adjusted Rand Index (ARI)
  - Silhouette Score  
- Visualize clusters using UMAP and dendrograms  

---

## 📂 Dataset

- **Source:** RecipeDB (Foodoscope)
- **Size:** ~118,000 recipes  
- **Protocols extracted:** ~270 unique cooking actions  

Each recipe contains:
- Ingredients  
- Nutritional values  
- Cooking steps (used for protocol extraction)

---

## 🧠 Models Used

| Model        | Description |
|--------------|------------|
| **SBERT** | General-purpose sentence embeddings |
| **FoodBERT (RecipeBERT)** | Food-domain pretrained model |
| **CookBERT** | Cooking-domain model (or BERT baseline) |
| **BioBERT** | Biomedical domain model |
| **PubMedBERT** | Scientific/medical corpus model |
| **Doc2Vec** | Classical embedding approach |

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Tokenization of recipe steps  
- Lemmatization (e.g., *chopping → chop*)  
- Removal of non-action words  

### 2. Protocol Labeling
Manual annotation into semantic categories:
- Cutting
- Mixing
- Heating
- Cleaning
- Transformation
- Resting
- Directional actions

### 3. Embedding Generation
- Contextual embeddings generated using transformer models  
- Optional inclusion of dictionary definitions  

### 4. Clustering
- Hierarchical Agglomerative Clustering (HAC)
- Distance metric: **Cosine similarity**
- Linkage: **Average**

### 5. Evaluation
- **Adjusted Rand Index (ARI)** → external validation  
- **Silhouette Score** → internal validation  

---

## 📊 Results

- **SBERT performed best** with highest ARI (~0.53)  
- Clear semantic clusters observed:
  - Cutting (chop, slice, dice)
  - Mixing (stir, blend, whisk)
  - Heating (boil, fry, bake)

- Domain-specific models (FoodBERT, CookBERT) performed moderately  
- Biomedical models (BioBERT, PubMedBERT) performed poorly in this domain  

---

## 📈 Visualizations

**Example outputs:**
* `sbert_dendrogram.png`
* `foodbert_dendrogram.png`
* `cookbert_dendrogram.png`
* `sbert_umap.png`
* `foodbert_umap.png`
* `cookbert_umap.png`

---

- 📌 **Dendrograms** (Hierarchical clustering)
- 📌 **UMAP plots** (2D embedding projection)
- 📌 Cluster distributions

Example outputs:
