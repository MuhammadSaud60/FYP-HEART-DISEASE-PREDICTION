# HeartCare: Web-Based Heart Disease Prediction Using Machine Learning

## Project Overview
Heart disease is a major cause of death worldwide. Early detection can help save many lives. However, medical tools like ECG are expensive and not available in many regions. 

The goal of this project is to develop a low-cost, easy-to-use, web-based tool to predict heart disease risk. The system uses routine health data provided by the user to make real-time predictions.


**Supervisor:** Prof. Muhammad Assad[cite: 3]  
**Institution:** Abdul Wali Khan Unversity Mardan
**Session:** 2021-2025[cite: 3]

## Dataset Information
The machine learning models were trained using the public UCI Heart Disease Dataset[cite: 1, 3]. 
* **Data Size:** 920 patient records collected from 4 locations (Cleveland, Hungary, Switzerland, and VA Long Beach)[cite: 1, 3].
* **Features Used:** The model takes 13 input features, including age, gender, blood pressure, cholesterol level, chest pain type, and maximum heart rate[cite: 1, 2, 3].

## Methodology and Preprocessing
To prepare the data for the machine learning models, the following steps were performed:
1. **Handling Missing Data:** Missing values were filled using the IterativeImputer method based on Random Forest algorithms[cite: 1, 2].
2. **Outlier Detection:** Boxplots were used to find and remove unusual data points that could lower model accuracy[cite: 1].
3. **Categorical Encoding:** LabelEncoder was used to convert text data (like Gender) into numerical format[cite: 1, 2].
4. **Feature Scaling:** MinMaxScaler was applied to rescale all numerical values into a 0 to 1 range for better performance[cite: 1, 2].

## Model Selection and Performance
We trained and evaluated three different machine learning models using Grid Search CV for hyperparameter tuning[cite: 1, 2]:
* **Support Vector Classifier (SVC):** Achieved an AUC score of 0.54[cite: 1, 3].
* **Random Forest Classifier:** Achieved an AUC score of 0.54[cite: 1, 3].
* **XGBoost Classifier:** Achieved the best performance with an AUC score of 0.94 and an overall accuracy of 86%[cite: 1, 3].

Because XGBoost showed the highest accuracy and the best ability to separate the classes, it was chosen as the final model for deployment[cite: 1, 3].

## Web Application Architecture
* **Frontend:** Built using HTML, CSS, and JavaScript to create a responsive and simple web form[cite: 1, 3].
* **Backend:** Developed using the Flask framework in Python[cite: 1, 3].
* **Integration:** The trained XGBoost model was saved using joblib/pickle and loaded into the Flask server[cite: 1, 2]. When a user submits their health numbers, the backend processes the data, runs it through the model, and displays the result ("Heart Disease" or "No Heart Disease") instantly on the screen[cite: 1, 3].

## How to Run the Project Local Layout
1. Clone this repository to your computer.
2. Install the required Python libraries using the command:
   ```bash
   pip install pandas numpy scikit-learn xgboost flask joblib
   python app.py
   
