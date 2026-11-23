# College Canteen Food Demand Prediction

A machine learning project built in **Orange Data Mining** that predicts the
demand level (**Low / Medium / High**) of college canteen food items.

Course: 26CSE1001T – Data Science and Artificial Intelligence (CA-3)
Author: Sandhya M, SRM Institute of Science and Technology, Kattankulathur

## Problem
Canteens need to know how much food to prepare. Preparing too much causes
wastage and too little causes shortages. This project classifies demand using
historical sales and daily campus conditions.

## Dataset
- 80 records, 8 columns (`college_canteen_demand_sample.csv`)
- Input features (7): DayOfWeek, Weather, StudentCount, ExamDay, CampusEvent,
  FoodItem, PreviousWeekSales
- Target: DemandLevel (Low 6, Medium 43, High 31)
- No missing values and no duplicate rows
- `college_canteen_future_input_20_records.csv` holds 20 new records used
  for prediction
- Source: [add the source link / credit here]

## Workflow
![Orange workflow](workflow.png)

CSV File Import → Select Columns → 5 classifiers → Test and Score →
Confusion Matrix / ROC Analysis. The Decision Tree then goes to Predictions
(with the new CSV) → Save Data.

**Widgets used:** CSV File Import, Data Table, Select Columns, Tree,
Random Forest, Naive Bayes, Logistic Regression, kNN, Test and Score,
Confusion Matrix, ROC Analysis, Predictions, Save Data

## Models and evaluation
Five classifiers were compared using stratified 2-fold cross-validation
repeated 3 times.

| Best model | Accuracy | Precision (macro) | Recall (macro) | F1 (macro) |
|---|---|---|---|---|
| Decision Tree | 97.50% | 98.59% | 91.90% | 93.34% |

The Decision Tree had the best accuracy, F1, precision and recall.
Logistic Regression had the best AUC in Orange.

![Results](results.png)

## How to run
1. Install [Orange](https://orangedatamining.com/).
2. Download this repository (green **Code** button → **Download ZIP**) and unzip it.
3. Open Orange and choose **File → Open** and select the `.ows` file.
4. Double-click each **CSV File Import** widget and re-select the matching CSV
   from the unzipped folder, since the original file paths were on my computer.

## Limitations
The dataset is small (80 records), so the model should be tested on more data
before real use in a canteen.

## Presentation
See `College_Canteen_Orange_Workflow1.pptx`.

## References
- Orange Data Mining: https://orangedatamining.com/
- Han, J., & Kamber, M. (2006). *Data Mining: Concepts and Techniques.*
