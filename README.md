# Price-Prediction-of-Cubic-Zirconia-Stones

Problem Statement
The objective of this project is to predict the price of cubic zirconia stones based on their physical and categorical attributes such as carat, cut, color, clarity, depth, table, and dimensions (x, y, z). Accurate price prediction is important in the jewelry and gemstone industry, where pricing decisions depend on a complex interplay of these features. By applying data preprocessing, exploratory analysis, and different machine learning algorithms, this project aims to identify the most important predictors of price and evaluate the effectiveness of linear and nonlinear models.

Data Cleaning and Preprocessing
The dataset was first cleaned and preprocessed. An unnecessary column was dropped, missing values in the depth attribute were imputed with the mean, and invalid rows with zero values for dimensions (x, y, z) were removed since they are not physically possible. Categorical variables such as cut, color, and clarity were encoded numerically, and skewed attributes (carat, y, z, and price) were transformed using a logarithmic transformation to reduce skewness.

Exploratory Data Analysis (EDA)
Exploratory analysis using pairplots and a correlation matrix revealed that the stone dimensions and carat weight are strongly correlated with price, and also highly correlated with each other, highlighting the presence of multicollinearity. Outlier detection and skewness checks were performed using boxplots to understand feature distributions and identify the need for scaling and transformations.

Model Building
Three different models were developed and evaluated. First, a baseline linear regression model was trained using scaled features to establish a benchmark. Next, Ridge Regression was applied to address multicollinearity and stabilize coefficients through L2 regularization. The best value of the regularization parameter alpha was determined using GridSearchCV. Finally, a Random Forest Regressor was trained as a nonlinear ensemble method capable of capturing feature interactions and complex patterns.

Model Evaluation
Model performance was evaluated using the R² score and Root Mean Squared Error (RMSE) on both training and test sets. Linear Regression achieved a test R² of 0.948, explaining about 95% of the variance in prices. Ridge Regression, with an optimized alpha of 50, produced similar results with strong interpretability of coefficients, identifying y, z, clarity, color, and x as the most influential features. Random Forest Regression significantly outperformed the linear models, achieving a test R² of 0.991 and the lowest RMSE of 0.098. Feature importance analysis revealed that the y dimension was by far the most important predictor, followed by carat, x, clarity, and color.

Conclusion
In conclusion, while Ridge Regression provided an interpretable model with insights into how each feature affects price, Random Forest delivered the most accurate predictions by capturing nonlinear relationships and feature interactions. Therefore, Random Forest is recommended as the final model for price prediction, whereas Ridge Regression remains useful when transparency and interpretability of coefficients are required.

