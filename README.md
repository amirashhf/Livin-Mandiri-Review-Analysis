# 💬 Sentiment & Topic Analysis of Livin' by Mandiri User Reviews

![Text Mining](https://img.shields.io/badge/Text-Mining-blue)
![NLP](https://img.shields.io/badge/NLP-Natural_Language_Processing-green)
![Sentiment Analysis](https://img.shields.io/badge/Sentiment-Analysis-yellow)
![Orange Data Mining](https://img.shields.io/badge/Orange-Data_Mining-F8981D)

## 📖 Overview
In the digital era, mobile banking applications like **Livin' by Mandiri** are essential for daily financial management in Indonesia. User reviews for such apps are a goldmine of feedback, containing a wide spectrum of opinions from high praise to critical technical issues. This project leverages the **Orange Data Mining** platform to perform a comprehensive text mining analysis on user reviews, aiming to uncover public sentiment, key emotions, and the most frequently discussed topics. The insights gathered can provide actionable guidance for developers to improve service quality.

## 📊 Dataset
* **Source:** A `.csv` file containing user reviews for the Livin' by Mandiri mobile application.
* **Content:** 12,366 user reviews.
* **Columns:** `uname` (username, as metadata) and `review` (the user's text comment).
* **Key Characteristic:** The dataset is primarily in Indonesian and contains no missing values.

## ⚙️ Project Workflow

![image](https://github.com/user-attachments/assets/7b45e4d6-bd95-4698-8b3e-319b9e12a453)

The entire analysis was conducted within Orange Data Mining, following a structured text mining pipeline:

1.  **Data Import & Pre-processing:** The review data was imported and processed using the `Preprocess Text` widget. This involved converting text to lowercase, tokenization, and removing Indonesian stopwords to clean the data for analysis.
2.  **Feature Extraction & Analysis:** Several parallel analyses were conducted on the cleaned corpus:
    * **Keyword Extraction:** Used **TF-IDF** to identify the most significant terms in the reviews.
    * **Sentiment & Emotion Analysis:** Applied a multilingual sentiment model to classify reviews as positive/negative and used the `Tweet Profiler` to analyze emotions based on Ekman's model (Joy, Surprise, Fear, etc.).
    * **Topic Modeling:** Used **Latent Dirichlet Allocation (LDA)** to discover 10 abstract topics from the review texts.
3.  **Classification Modeling:**
    * The `Bag of Words` widget was used to create a numerical feature representation of the text.
    * A **Naive Bayes** classifier was trained to categorize reviews into three sentiment classes: *Positive*, *Negative*, and *Neutral*.
    * The model's performance was evaluated using 10-fold cross-validation, with results visualized in a Confusion Matrix.

## 📈 Key Findings & Results

#### 🔑 Keyword Extraction (TF-IDF)
The most important terms frequently discussed by users were: **`update`**, **`aplikasi`** (application), **`livin`**, **`transaksi`** (transaction), and **`transfer`**. This indicates a strong focus on core app functionality and recent updates.

#### 😊 Sentiment & Emotion Analysis
* The dominant emotion detected in the reviews was **Joy** (7,071 instances), suggesting a generally positive user experience.
* However, negative reviews were significant and often pointed to technical issues, using terms like **`sering gangguan`** (frequent disruptions) and **`bug banyak`** (many bugs).

#### 🔬 Topic Modeling (LDA)
The model successfully identified 10 distinct topics, revealing key areas of user feedback, including:
* Issues with **app updates**.
* Problems related to **failed transactions and transfers**.
* The user experience of different app versions (**"Livin' Biru"** vs. **"Livin' Kuning"**).
* Concerns about **security and login** processes.

#### 🎯 Classification Model Performance
The **Naive Bayes** model demonstrated exceptional performance in classifying the pre-labeled sentiment data.
* **Accuracy, F1-Score, Precision, and Recall:** All metrics achieved a perfect score of **1.000**.
* **Confusion Matrix:** The model correctly classified all 12,366 instances with **zero misclassifications**, confirming that the extracted text features were highly effective in distinguishing between sentiment classes.

## 🚀 How to Use This Project
This project was built entirely in Orange Data Mining.
1.  **Download and install** [Orange Data Mining](https://orangedatamining.com/download/).
2.  Clone this repository.
3.  Open the `.ows` workflow file included in this repository to explore the interactive analysis pipeline.
  
