# stroke-prediction
### A Python project that predicts a patient's likeliness to suffer a stroke based on various environmental and health factors.

This project is an exploratory analysis of hospital patient data in order to predict the most at-risk groups for strokes and investigate possible relationships among these risk factors. The dataset was downloaded from kaggle, containing factors including patient ID, gender, age, whether they have hypertension, whether they have heart disease, whether they have been married, work type, residence type, average blood glucose level, body mass index (BMI), whether they smoke, and whether they have ever had a stroke.

### Data pre-processing 
Data values were missing from the BMI column, so missing values were replaced with the average of this column (28.89 kg/m<sup>2</sup>). Data values were also missing from the smoking status column, so a separate "Unknown" category was created for these missing values. Nominal categorical columns were standardized by converting 0 to "No" and 1 to "Yes".

### Numerical Regression
Potential associations between the continuous numerical data were considered (average glucose levels, age, and BMI). These columns were compared in pairs with scatter plots and a linear regression model, and the fit equation, Pearson correlation coefficient (r), and Spearman correlation coefficient (&rho;) were displayed. A quadratic regression model was also fit to the relationship between BMI and age.

### Numerical Correlations with Stroke
The numerical columns (age, BMI, and average glucose level) were evaluated for their effects on patient stroke rate. For each numerical column, a t-test was conducted with the stroke column to compare the distribution means of patients who have had a stroke with patients who have not experienced a stroke. Violin plots and percent stacked bar charts were used to visualize these distributions.

### Categorical Correlations with Stroke
The categorical columns (gender, hypertension, heart disease, marital status, work type, residence type, and smoking status) were then evaluated for their effects on patient stroke rate. Chi-squared tests were conducted between each categorical factor and the stroke column in a contingency table. A dependency on age may be responsible for the small p-values associated with some of these factors.

### Machine Learning for Stroke Prediction
The risk factors identified to affect stroke rates the most were age, average glucose level, hypertension status, and heart disease status. A "k nearest neighbors" algorithm (kNN) was implemented in order to predict the stroke risk of the patient based on these known properties. The algorithm was trained with 70% of the dataset using known stroke rates, and the accuracy of the model was evaluated with the remaining 30%. The accuracy maxed out at about k=13 neighbors, leading to a model with about 95% accuracy.


