# Overview

This repository contains the code for a Business Success Model that integrates data analysis, machine learning, and natural language processing techniques. The model aims to predict and analyze the success of businesses, leveraging the Yelp dataset, including information about businesses, reviews, and users.

# Jupyter Notebooks

## 1. `Business_Success_Model.ipynb`

### Notebook Contents

- **Data Preprocessing:**
  - Loading and preprocessing the Yelp dataset.
  - Handling null values, exploring data distribution, and merging relevant dataframes.

- **Fine-tuning BERT for Sequence Classification:**
  - Fine-tuning the BERT (Bidirectional Encoder Representations from Transformers) model for sequence classification to predict restaurant ratings based on customer reviews.

- **Predicting and Aggregating Ratings:**
  - Utilizing the fine-tuned BERT model to predict ratings for a batch of texts.
  - Aggregating predictions and saving them to a CSV file.

- **Creating the Final Dataset for Classifier Input:**
  - Combining predicted ratings with the original review data.
  - Calculating final review ratings and aggregating business-related information.

## 2. `Train_and_evaluate_classifiers.ipynb`

### Notebook Contents

- **Importing Necessary Libraries:**
  - Importing libraries for classification and evaluation.
  - Mounting Google Drive to access files.

- **Data Loading:**
  - Loading the final dataset generated from the Business_Success_Model notebook.

- **Training and Evaluating Classifiers:**
  - Training Random Forest, XGBoost, and Gaussian Mixture Model (GMM) classifiers.
  - Evaluating classifiers using metrics such as accuracy, precision, recall, and F1 score.
  - Extracting and plotting feature importance for Random Forest and XGBoost.

# Results

   - ## Gaussian Mixture Model (GMM) Metrics:

      - **Accuracy:** 0.397
      - **Precision:** 0.751
      - **Recall:** 0.295
      - **F1 Score:** 0.424
      - **Confusion Matrix:**
        | Actual\Predicted | Positive | Negative |
        |------------------|----------|----------|
        | Positive         | 420      | 176      |
        | Negative         | 1272     | 532      |

  - ## Random Forest Metrics:

    - **Accuracy:** 0.954
    - **Precision:** 0.948
    - **Recall:** 0.993
    - **F1 Score:** 0.970
    - **Confusion Matrix:**
      | Actual\Predicted | Positive | Negative |
      |------------------|----------|----------|
      | Positive         | 497      | 99       |
      | Negative         | 12       | 1792     |

    - **Random Forest Feature Importance:**
      | Rank_RF | Feature               | Importance |
      |---------|-----------------------|------------|
      | 1       | std_review_ratings    | 0.165      |
      | 2       | mean_review_ratings   | 0.152      |
      | 3       | useful_votes_mean     | 0.145      |
      | 4       | review_count          | 0.135      |
      | 5       | cool_votes_mean       | 0.131      |
      | 6       | funny_votes_mean      | 0.126      |
      | 7       | business_rating       | 0.081      |
      | 8       | median_review_ratings | 0.064      |

- ## XGBoost Metrics:
  
    - **Accuracy:** 0.853
    - **Precision:** 0.857
    - **Recall:** 0.965
    - **F1 Score:** 0.908
    - **Confusion Matrix:**
      | Actual\Predicted | Positive | Negative |
      |------------------|----------|----------|
      | Positive         | 306      | 290      |
      | Negative         | 63       | 1741     |

    - **XGBoost Feature Importance:**
      | Rank_XGB | Feature               | Importance |
      |----------|-----------------------|------------|
      | 1        | business_rating       | 0.179      |
      | 2        | funny_votes_mean      | 0.124      |
      | 3        | cool_votes_mean       | 0.120      |
      | 4        | useful_votes_mean     | 0.118      |
      | 5        | review_count          | 0.117      |
      | 6        | median_review_ratings | 0.117      |
      | 7        | mean_review_ratings   | 0.114      |
      | 8        | std_review_ratings    | 0.112      |

# Instructions

1. **Clone the repository:**

   ```bash
   git clone https://github.com/AB-Codes29/business_success_model.git

2. **Additional Resources**

- **Yelp Training Sets:**
  - [Business Data](https://drive.google.com/file/d/1nEZMt7hZdnoTmi4nFROPSC6COo7xiusm/view?usp=sharing)
  - [Review Data](https://drive.google.com/file/d/1CMIJUMffIbmZzjjC_GryjUImZHp3QtGj/view?usp=sharing)
  - [User Data](https://drive.google.com/file/d/1DtqKMqtTEfQKFJiKEUavuMR5VmVDk6dR/view?usp=sharing)

- **Predictions and Models:**
  - [Predictions CSV](https://drive.google.com/file/d/18eu8ibTyaM5ClAb5MWIncKdsBjZCWjuc/view?usp=sharing)
  - [BERT Model](https://drive.google.com/drive/folders/1wsGkay3O__A3oWPiIoMlHd86-loa2l_h?usp=sharing)
