# Disease Diagnosis using Topic Modeling  
**Computational Linguistics and NLP – Term Project**

## Project Overview

This project explores the use of topic modeling techniques for automatic **disease diagnosis** based on textual medical descriptions. The system identifies the medical domain of a query (ear, nose, musculoskeletal, or respiratory) and then further narrows it down based on user-provided descriptions. The pipeline leverages domain-specific medical knowledge extracted from textbook chapters and models topics using three different approaches to determine the most effective technique for diagnosis support.

---

## Dataset

Three chapters were extracted from a **standard medical book**, focusing on:
- Ear and Nose related conditions
- Musculoskeletal-related conditions
- Respiratory systems-related conditions

These chapters formed the **raw corpus** for training the topic models.

---

## Data Preprocessing (`DataPreprocessing.ipynb`)

The raw text was subjected to:
- **Text normalization** (lowercasing, punctuation removal)
- **Stop word removal** using NLTK’s standard list
- **Domain-specific stop word removal** (e.g., "patient", "examination", "diagnosed")

This step ensured that only relevant and informative words were retained for topic extraction.

---

## Topic Modeling (`ModellingusingLSA_LDA_Corex.ipynb`)

Three different unsupervised topic modeling techniques were evaluated:
1. **Latent Semantic Analysis (LSA)**
2. **Latent Dirichlet Allocation (LDA)**
3. **CorEx (Correlation Explanation)**

After analyzing the coherence scores and interpretability of generated topics, **LSA** was chosen as the best-performing model for further diagnosis tasks.

---

## Results (`Results.ipynb`)

- Topic keywords and clusters were visualized.
- Model performance and coherence values were compared.
- A sample of user queries was tested for classification accuracy.
- The LSA model showed the most semantically coherent results aligned with medical categories.

---

## Final Diagnosis Pipeline

The system accepts a **free-text query** from a user describing symptoms. The diagnosis process is as follows:

1. **Primary classification**: The query is first classified into one of the high-level categories:
   - Ear/Nose
   - Musculoskeletal
   - Respiratory

2. **Secondary classification**: Within the identified category, the system performs **sub-topic identification** using the LSA model to map the query to more specific conditions or areas of concern.
