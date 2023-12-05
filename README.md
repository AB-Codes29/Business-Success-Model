# Restaurant Success Prediction Model

## Overview

This Python script is designed to predict the success of restaurants based on Yelp reviews. The model uses an AutoRegressive (AR) time series analysis approach to forecast future restaurant success. The main goal is to predict whether a restaurant is likely to close within a 4-year period.

## Files

- **Business_Success_Model.ipynb**: The main Jupyter Notebook containing the code.
- **yelp_training_set_business.csv**: Input file containing business data from Yelp.
- **yelp_training_set_review.csv**: Input file containing Yelp reviews.
- **stars.csv**: Synthetic test data for the stars attribute.
- **yelp_training_set_business_corrected.csv**: Output file with corrected business data.
- *Corresponding files can be downloaded [here](https://drive.google.com/drive/folders/1aXe0SP_RnQmtlpT7Kd4X_IaijVj_X6BW?usp=share_link)*

## Dependencies

The script requires the following Python libraries:

- pandas
- numpy
- statsmodels

## Setup

1. **Create a Virtual Environment:**

   ```bash
   python -m venv venv
   ```

2. **Activate the Virtual Environment:**

   - On Windows:

     ```bash
     venv\Scripts\activate
     ```

   - On macOS/Linux:

     ```bash
     source venv/bin/activate
     ```

Install the dependencies using:

```bash
pip install pandas numpy statsmodels
```

## How to Run

1. Open the Jupyter Notebook `Business_Success_Model.ipynb` in a Jupyter environment.
2. Ensure that the required input files (`yelp_training_set_business.csv`, `yelp_training_set_review.csv`, and `stars.csv`) are in the same directory as the notebook.
3. Run the cells in the notebook sequentially.

## Code Structure

1. **Data Preprocessing**
    - Reads business and review data from CSV files.
    - Corrects the `review_count` attribute in the business data.
    - Handles duplicates in the datasets.

2. **Time Series Analysis**
    - Utilizes AutoRegressive (AR) modeling for time series analysis.
    - Filters businesses based on a minimum review threshold.
    - Segregates businesses based on review counts.

3. **Prediction**
    - Builds an AR model for each restaurant based on historical review ratings.
    - Averages the last year's reviews to predict future success.
    - Classifies restaurants as "Successful" or "Unsuccessful" based on a threshold.

4. **Output**
    - Generates a CSV file (`Prediction.csv`) containing the predicted success of each restaurant.

## Results

The script outputs a CSV file (`Prediction.csv`) with the predicted success status of each restaurant based on the given criteria. The file includes business IDs, review stars, and the predicted success label.

## Notes

- The synthetic test data (`stars.csv`) is generated for model testing purposes.
- The minimum review threshold (`min_thresh`) is set to 21, assuming 3 reviews per day.
- The model predicts success based on an average review rating over a specified period
