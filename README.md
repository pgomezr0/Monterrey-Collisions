# Traffic Accident Prediction in Monterrey, Mexico

## **Overview**
Monterrey, Mexico, one of the largest cities in the country, has experienced a significant increase in traffic congestion and accidents in recent years. The city, known as the capital of Nuevo León, tops the list of traffic delays, with an average of **116 hours of delay per year** and a **travel speed of 32 km/h** on average. This congestion, combined with weather variability and human factors, is correlated with traffic accidents.

This project aims to predict traffic accident severity based on historical accident data and weather conditions. The goal is to leverage machine learning techniques, initially a **Decision Tree** model, to identify patterns and provide insights that can help reduce accidents and improve road safety.

---

## **Context**
Traffic accidents are influenced by a wide range of factors:
1. **Human Behavior**: Driver's age, gender, alcohol consumption.
2. **Road and Vehicle Conditions**: Number of vehicles involved, accident type, cause of accident.
3. **Weather Conditions**: Precipitation, visibility, wind speed, and temperature.

By analyzing historical accident data combined with weather behavior, this project seeks to understand and predict accident outcomes, focusing on **severity classification**:
- **Just Damages**
- **Non-Fatal**
- **Fatal**

---

## **Problem Statement**
The rapid increase in traffic volume and variability in weather conditions in Monterrey creates a need for tools to help predict and potentially mitigate traffic accidents. Specifically, this project aims to:
1. Classify accidents by their severity.
2. Explore the relationship between weather conditions and accident outcomes.
3. Lay the foundation for future studies and applications in traffic safety and urban planning.

---

## **Dataset**
The dataset contains approximately 30,000 records of traffic accidents in Monterrey. Key features include:
- **Accident Details**: 
  - Type of accident (`tipo_de_accidente`)
  - Cause of accident (`causaacci`)
  - Driver details (`gender`, `id_edad`, `alcohol` consumption)
  - Number of vehicles involved by type (e.g., heavy, light, two-wheelers)
- **Weather Conditions**:
  - Temperature (`temp`, `feelslike`)
  - Precipitation (`precip`, `precipprob`, `precipcover`)
  - Wind (`windspeed`, `windgust`, `winddir`)
  - Visibility, cloud cover, and severe risk index (`severerisk`)
- **Geographic and Temporal Context**:
  - Location (`nombre_de_asentamiento`, `nombre_de_la_vialidad`)
  - Date and time of the accident

The target variable is **`clasacc`**, which classifies accidents into three categories:
- `Fatal`
- `Non-Fatal`
- `Just Damages`

---

## **Solution**
### **Phase 1: Decision Tree Model**
The project currently focuses on building an initial **decision tree model** to predict accident severity. 

#### **Steps Taken**
1. **Data Preprocessing**:
   - Encoded categorical variables (e.g., accident type, gender).
   - Processed weather features (e.g., precipitation, visibility) for modeling.
   - Handled missing values and prepared features like georeference and time.

2. **Feature Selection**:
   - Key features included weather conditions, accident type, driver details, and vehicle counts.
   - Time and geographic features were explored but may require further refinement.

3. **Model Development**:
   - A **DecisionTreeClassifier** was trained to classify accidents into severity categories (`just damages`, `non-fatal`, `fatal`).
   - Addressed the imbalanced dataset using oversampling (SMOTE) and class weighting.

4. **Evaluation**:
   - The model's performance was assessed using rand confusion matrices.
   - Initial results show an overfitted model, which requires handling the unbalanced data.

---

## **Current Status**
This project has reached its first milestone: creating and evaluating an initial decision tree model. The interplay between human, environmental, and geographic factors requires further exploration and testing.

---

## **Future Potential**
There are several directions for improvement and expansion:
1. **Advanced Modeling**:
   - Expriment with parameter-tuning
   - Experiment with ensemble models (Random Forests, Gradient Boosting).
   - Explore neural networks or other complex models for deeper insights.
2. **Integration of Real-Time Data**:
   - Incorporate real-time weather forecasts or live traffic data for predictive applications.
3. **Policy Recommendations**:
   - Use insights from the model to propose actionable safety measures, like adjusting traffic signals, improve road conditions, or warning drivers during adverse weather.

---

## **Challenges**
1. **Class Imbalance**:
   - The dataset is heavily skewed towards `just damages`, making it difficult for the model to accurately predict `fatal` and `non-fatal` accidents.
2. **Complex Interactions**:
   - The relationships between weather, human behavior, and accidents are intricate and may require more sophisticated feature engineering.

---

## **How to Use**
1. **Requirements**:
   - Python 3.x
   - Libraries: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

2. **Run the `final_dataset` Notebook**:
   - Preprocess the data: Handle missing values, encode categorical features, and scale numerical ones.
   - Train the decision tree model: Use the `DecisionTreeClassifier` in `scikit-learn`.
   - Evaluate the model: Generate a classification report and visualize the decision tree.

---

### **Author's Notes**

This project sets a foundation for understanding and predicting traffic accidents in Monterrey, Mexico. While the decision tree model marks the first step, there is immense potential to build on this work with more advanced techniques and additional data sources.

The ultimate goal is to contribute to safer roads in Monterrey by leveraging data-driven insights. Future iterations of this project could inform urban planning, traffic management, and accident prevention strategies.

Contributions, feedback, and suggestions for improvement are welcome!
