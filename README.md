# AI/ML Engineering Internship - DevelopersHub Corporation

This project is a part of my **AI/ML Engineering Internship** at **DevelopersHub Corporation**, Islamabad.

## Internship Details

- **Company:** DevelopersHub Corporation, Islamabad 🇵🇰
- **Internship Period:** July - August 2025

# House Price Prediction Project

## Task Objective

This project implements a comprehensive machine learning solution for predicting house prices using property features such as size, bedrooms, bathrooms, and various amenities. The goal is to develop accurate regression models that can estimate property values based on available features, providing valuable insights for real estate decision-making.

## Dataset Used

**Dataset**: Housing Price Prediction Dataset  
**Source**: Kaggle - https://www.kaggle.com/datasets/harishkumardatalab/housing-price-prediction 
**Size**: 545 samples with 13 features  
**Features**:
- **Numerical Features**: price, area, bedrooms, bathrooms, stories, parking
- **Categorical Features**: mainroad, guestroom, basement, hotwaterheating, airconditioning, prefarea, furnishingstatus

**Dataset Statistics**:
- Price Range: $1,750,000 - $13,300,000
- Average Price: $4,766,729
- No missing values detected
- Contains 2.8% outliers in price data

## Models Applied

### 1. Linear Regression
- **Purpose**: Baseline model for interpretability and performance comparison
- **Features**: 12 engineered features after preprocessing
- **Training**: 80% training set, 20% test set
- **Cross-validation**: 5-fold CV for robust evaluation

### 2. Gradient Boosting Regressor
- **Purpose**: Advanced ensemble model for capturing non-linear relationships
- **Parameters**: n_estimators=100, learning_rate=0.1, max_depth=6
- **Features**: Same feature set as Linear Regression
- **Training**: Same train-test split for fair comparison

## Key Results and Findings

### Model Performance Comparison

| Metric | Linear Regression | Gradient Boosting |
|--------|-------------------|-------------------|
| **Test MAE** | $979,680 | $1,045,788 |
| **Test RMSE** | $1,331,071 | $1,419,330 |
| **Test R²** | 0.6495 | 0.6015 |
| **CV MAE** | $746,881 | $805,435 |

### Best Performing Model
**Linear Regression** outperformed Gradient Boosting with:
- **6.3% lower MAE** on test set
- **Better generalization** (smaller gap between training and test performance)
- **Higher interpretability** through coefficient analysis

### Key Insights

#### Most Important Features
1. **Area** - Strongest correlation with price (0.54)
2. **Bathrooms** - Second most important feature (0.52)
3. **Stories** - Building height impact (0.42)
4. **Parking** - Parking availability (0.38)
5. **Bedrooms** - Number of bedrooms (0.37)

#### Model Performance
- **Average Prediction Error**: ~$980K (MAE)
- **Variance Explained**: ~65% of price variance captured
- **Cross-validation Stability**: Consistent performance across folds

### Data Insights

#### Price Distribution
- **Skewed Distribution**: Most houses priced below $6M
- **Outliers**: 15 properties (2.8%) priced significantly higher
- **Market Range**: Concentrated in $2M-$7M range

#### Feature Relationships
- **Positive Correlations**: Area, bathrooms, and stories show strongest positive relationships with price
- **Categorical Impact**: Air conditioning and preferred area significantly increase property value
- **Location Factors**: Main road access and furnishing status influence pricing

## Technical Implementation

### Preprocessing Pipeline
1. **Data Cleaning**: No missing values found
2. **Categorical Encoding**: Label encoding for all categorical variables
3. **Feature Scaling**: StandardScaler applied to numerical features
4. **Outlier Detection**: IQR method for identifying extreme values

### Model Training
- **Feature Engineering**: 12 final features after preprocessing
- **Train-Test Split**: 80-20 split with random state 42
- **Cross-validation**: 5-fold CV for robust evaluation
- **Hyperparameter Tuning**: Optimized parameters for Gradient Boosting

### Evaluation Metrics
- **MAE**: Mean Absolute Error for interpretable error measurement
- **RMSE**: Root Mean Square Error for penalizing larger errors
- **R²**: Coefficient of determination for variance explanation
- **Cross-validation**: Ensures model robustness

## Recommendations

### For Production Use
1. **Deploy Linear Regression** as the primary model due to better performance and interpretability
2. **Regular Model Retraining** as market conditions change
3. **Feature Monitoring** to track data quality and drift

### For Model Improvement
1. **Collect More Data** for outlier properties to improve generalization
2. **Feature Engineering** - consider interaction terms and polynomial features
3. **Ensemble Methods** - combine multiple models for better performance
4. **Hyperparameter Tuning** - optimize Gradient Boosting parameters

### Business Applications
1. **Property Valuation** for real estate agencies
2. **Investment Analysis** for property investors
3. **Market Research** for understanding price drivers
4. **Risk Assessment** for mortgage lending

## Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

### Usage
1. Ensure `Housing.csv` is in the same directory
2. Run the Jupyter notebook `house_price_prediction.ipynb`
3. Follow the analysis workflow from data loading to final predictions

### File Structure
```
House-Price-Prediction/
  ├── README.md                           # This file
  ├── house_price_prediction.ipynb        # Main analysis notebook
  └── Housing.csv                         # Dataset file
```

## Skills Demonstrated

- **Regression Modeling**: Linear and ensemble regression techniques
- **Feature Engineering**: Scaling, encoding, and selection
- **Model Evaluation**: MAE, RMSE, cross-validation
- **Data Visualization**: Comprehensive EDA and model analysis
- **Real Estate Analytics**: Domain-specific insights and interpretation


**Note**: This project demonstrates a complete machine learning workflow for house price prediction, suitable for educational purposes and as a foundation for production real estate valuation systems.
