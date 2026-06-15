# World Cup Predictor: Predicting the 2026 FIFA World Cup with Machine Learning

**Graduate Team Project**  
**Master of Information and Data Science**  
**University of California, Berkeley**

**Chase Foster**

---

## Overview

This project applies machine learning techniques to predict match outcomes for the 2026 FIFA World Cup using historical international soccer match data, FIFA rankings, custom ELO ratings, and recent team performance metrics.

Rather than relying on post-match statistics, our models were built exclusively using information available before kickoff, allowing them to generate realistic pre-match predictions. We developed and compared multiple machine learning models, evaluated their performance on unseen data, and generated complete tournament predictions for the 2026 FIFA World Cup.

---

## Objectives

The goals of this project were to:

- Predict match outcomes for the 2026 FIFA World Cup.
- Compare multiple machine learning algorithms for multi-class classification.
- Engineer informative pre-match features using historical match data.
- Evaluate model performance using realistic time-based validation.
- Generate tournament predictions using the best-performing model.

---

## Dataset

### Sources

- Historical international soccer match results (Kaggle)
- FIFA World Rankings

### Data Summary

- 49,071 historical international matches
- FIFA rankings from 1992–2024
- Final modeling dataset containing **25,691 matches** and **15 engineered features** after merging, filtering, and feature engineering. :contentReference[oaicite:1]{index=1}

### Feature Engineering

Features included:

- Custom ELO ratings
- FIFA ranking differences
- FIFA ranking sums
- Recent team form (previous five matches)
- Goals scored and conceded
- Match type (friendly vs. competitive)
- Neutral-site indicator

Only information available prior to kickoff was used for prediction. 

---

## Methodology

### Data Preparation

- Data cleaning
- Feature engineering
- Historical ELO calculation
- Time-based train/validation/test split (60/20/20)

A chronological split was used to better simulate real-world forecasting by training on older matches and evaluating on newer matches rather than using a random split. 

---

## Models

Several predictive approaches were implemented and compared.

### Baseline Model

- Higher ELO rating predicts the winner

### Logistic Regression

- Multinomial logistic regression
- TensorFlow implementation
- Softmax output layer
- Hyperparameter tuning using Keras Tuner

### Feedforward Neural Network

- Three hidden layers
- ReLU activation
- Softmax output layer
- TensorFlow / Keras implementation

### Tree-Based Models

- Decision Tree
- Random Forest
- Gradient Boosting
- XGBoost (binary comparison)

Gradient Boosting was selected as the final tree-based model after demonstrating the strongest balance between overall accuracy and draw prediction. 

---

## Model Performance

| Model | Test Accuracy |
|--------|--------------:|
| Baseline | 59.44% |
| Logistic Regression | **60.89%** |
| Neural Network | **60.82%** |
| Gradient Boosting | **60.58%** |

Although all machine learning models improved upon the baseline, predicting draws remained a significant challenge across all approaches. Gradient Boosting achieved the highest recall for draw outcomes and was selected as the final model for tournament predictions. 

---

## Results

Key findings include:

- Machine learning models consistently outperformed the ELO-only baseline.
- Logistic Regression, Neural Networks, and Gradient Boosting achieved similar predictive performance.
- Draw outcomes were substantially more difficult to predict than home or away wins.
- Feature engineering using ELO ratings, FIFA rankings, and recent team form improved predictive performance over the baseline.
- The trained models were used to generate complete predictions for the 2026 FIFA World Cup tournament. 

---

## Repository Structure

```
world-cup-predictor/

│── README.md
│── LICENSE
│── .gitignore

├── data/
│   Datasets

├── models/
│   Saved machine learning models

├── predictions/
│   2026 World Cup prediction outputs

├── final_report/
│   Final written report

├── presentation/
│   Final project presentation

└── results/
│   Model comparison & final prediction visualizations

└── visualizations/
    Exploratory data analysis & model visualizations
```

---

## My Contributions

This project was completed as part of a graduate team in the UC Berkeley Master of Information and Data Science program.

My primary contributions included:

- Researching machine learning methods for sports prediction
- Pair programming throughout model development
- Developing and evaluating tree-based models
- Writing the **Methods**, **Experiments**, and **Model Comparison** sections of the final report
- Assisting with model evaluation and interpretation of results

The project was completed collaboratively, with all team members contributing to notebook development through pair programming.

---

## Technologies Used

### Programming

- Python

### Machine Learning

- TensorFlow
- Keras
- scikit-learn
- XGBoost

### Data Analysis

- pandas
- NumPy

### Visualization

- matplotlib
- seaborn

---

## Skills Demonstrated

- Machine Learning
- Multi-class Classification
- Feature Engineering
- Predictive Modeling
- Neural Networks
- Tree-Based Models
- Model Evaluation
- Hyperparameter Tuning
- Data Preprocessing
- Sports Analytics
- Team Collaboration

---

## Future Work

Potential extensions include:

- Incorporating player-level statistics and injury reports
- Exploring additional ensemble learning techniques
- Expanding feature engineering using advanced soccer metrics
- Improving draw prediction through alternative class-balancing methods
- Updating predictions as FIFA rankings evolve leading into the 2026 World Cup

---

## Acknowledgments

This project was completed as part of the Master of Information and Data Science program at the University of California, Berkeley.

Special thanks to my teammates for their collaboration throughout the project.

---

## Contact

If you have questions about this project or would like to discuss the methodology, feel free to connect with me on LinkedIn.
