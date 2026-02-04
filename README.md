# Practical Machine Learning: Weight Lifting Exercise Prediction

## Project Overview

This project predicts exercise quality using accelerometer data from weight lifting exercises. The analysis applies machine learning techniques to classify lifting performance into 5 categories (A, B, C, D, E) based on sensor measurements from belt, forearm, arm, and dumbbell locations.

## Dataset

- **Source**: Groupware@LES HAR Dataset
- **Reference**: Velloso, E., Bulling, A., Gellersen, H., Ugulino, W., & Fuentes, H. (2013)
- **Training observations**: 19,622
- **Test observations**: 20
- **Original variables**: 160
- **Predictor variables after cleaning**: 52

## Model Performance

- **Algorithm**: Random Forest with 5-fold cross-validation
- **Best tuning parameter**: mtry = 2
- **Accuracy**: 99.14%
- **Out-of-Sample Error**: 0.86%

## Files

- `PML_Analysis.Rmd` - R Markdown analysis document with complete code and results
- `index.html` - HTML report for web viewing
- `README.md` - This project documentation
- `.gitignore` - Git configuration file

## How to Run

1. Open `PML_Analysis.Rmd` in RStudio
2. Install required packages: `caret`, `ranger`, `ggplot2`, `doParallel`
3. Knit the document to generate the HTML report

```r
install.packages(c("caret", "ranger", "ggplot2", "doParallel"))
```

## Key Results

The Random Forest model achieves exceptional performance with 99.14% accuracy on the validation set. Class-specific metrics:

| Class | Sensitivity | Specificity | Pos Pred Value |
|-------|-------------|------------|-----------------|
| A     | 0.9957      | 0.9988     | 0.9974          |
| B     | 0.9902      | 0.9958     | 0.9900          |
| C     | 0.9896      | 0.9972     | 0.9898          |
| D     | 0.9879      | 0.9979     | 0.9930          |
| E     | 0.9949      | 0.9993     | 0.9955          |

## Data Preprocessing Steps

1. Removed columns with >95% missing values (107 columns)
2. Removed non-predictive columns (X, user_name, timestamps, window info)
3. Retained 52 predictor variables
4. Split data into 70% training and 30% validation sets

## Cross-Validation Strategy

5-fold cross-validation was used to:
- Provide robust error estimates
- Reduce bias and variance
- Balance computational efficiency with reliability
- Prevent overfitting

## Author

Your Name

## Date

November 5, 2025
