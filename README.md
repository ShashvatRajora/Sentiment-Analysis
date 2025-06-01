# 📘 Kindle Review Sentiment Analysis with Word2Vec

This project performs **sentiment analysis** on Kindle product reviews using **Word2Vec embeddings** and a logistic regression classifier. The goal is to classify each review as **positive**, **negative**.

---

##  Project Highlights

-  Cleaned and preprocessed real Kindle reviews.
-  Transformed raw text into **Word2Vec vector representations** (capturing semantic meaning).
-  Trained a classifier (Logistic Regression) on top of Word2Vec embeddings.
-  Achieved **high accuracy**, demonstrating Word2Vec's ability to understand context better than traditional methods.
-  Saved and reused the trained models for inference on new reviews.

---

## Why Word2Vec?

While traditional approaches like Bag-of-Words and TF-IDF treat words as independent tokens, **Word2Vec** maps each word into a continuous vector space, capturing **semantic relationships and contextual similarity**. For example, the words "excellent" and "great" will have similar vector representations, allowing the model to generalize better across varying vocabulary.

---

## 🛠Steps Performed

### 1. **Data Preprocessing**
- Removed special characters, HTML tags, URLs, and stopwords.
- Lowercased all review text.
- Performed lemmatization for standardizing word forms.
- Tokenized the cleaned text for training.

### 2. **Training the Word2Vec Model**
- Used Gensim's `Word2Vec` to learn 100-dimensional word embeddings from the tokenized reviews.
- Saved the Word2Vec model for reuse in inference and feature extraction.

### 3. **Feature Vectorization**
- Represented each review as the **average of its Word2Vec vectors**.
- This captures the overall meaning of the sentence in a dense vector form.

### 4. **Model Training**
- Trained a **Logistic Regression** classifier using the averaged Word2Vec vectors.
- Evaluated the model’s accuracy using a held-out test set.

### 5. **Saving Models**
- Persisted both the **Word2Vec embedding model** and the **classifier** using Gensim and Joblib.
- Enables future sentiment predictions without retraining.

---

## Prediction Example

You can use the saved models to predict sentiment on any new review:

```python
print(predict_sentiment("The beginning was confusing, but I ended up loving the story."))
# Output: 'Positive'
```

---

## Acknowledgement

This dataset is taken from Amazon product data, Julian McAuley, UCSD website. http://jmcauley.ucsd.edu/data/amazon/

License to the data files belong to them.

