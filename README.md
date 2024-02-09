# Patient Survival Prediction Deep Learning

## 🧾**Description:** 
Getting a rapid understanding of the context of a patient’s overall health has been particularly important during the COVID-19 pandemic as healthcare workers around the world struggle with hospitals overloaded by patients in critical condition. Intensive Care Units (ICUs) often lack verified medical histories for incoming patients. A patient in distress or a patient who is brought in confused or unresponsive may not be able to provide information about chronic conditions such as heart disease, injuries, or diabetes. Medical records may take days to transfer, especially for a patient from another medical provider or system. Knowledge about chronic conditions can inform clinical decisions about patient care and ultimately improve patient survival outcomes.


## 🧭 **Problem Statement:** 
The target feature is **hospital_death** which is a binary variable. The task is to classify this variable based on the other 84 features step-by-step by going through each day's task. The scoring metric is Accuracy/Area under the ROC curve.

## Project Summary: 

### 💡 Observations
* Dataset have 
    
    178 Numerical features Column, 
    8 categorical features Column,  


### Data preprocessing 
- Handling null values 
74/178 features have more than 50% null values
![image](https://github.com/Surendraprajapat18/Patient-Survival-Prediction-Deep-Learning/assets/97840357/8786a281-e205-4b74-813f-fe3d8c9e0dc6)

### Exploratory Data Analysis
- 0 - patient not survive 

- 1 - patient survive
![image](https://github.com/Surendraprajapat18/Patient-Survival-Prediction-Deep-Learning/assets/97840357/2da9c8dc-dcc8-4afa-a33a-8f4178356cb8)

### One Hot Encoding 
After addressing null values and handling features with over 50% null values, there are 5 categorical features in the dataset that require conversion into numeric values. We will employ **One Hot Encoding** for this purpose.

### Feature Engineering and Model Building
#### Model-1: Creating the Basic Deep Learning Model
![image](https://github.com/Surendraprajapat18/Patient-Survival-Prediction-Deep-Learning/assets/97840357/c06fb4d7-e4b0-4066-80d5-10283b455dc7)

**💡 Conclusion from Model 1**
    
- There is a large fluctuation in the validation loss using this model.
- The recall evaluation metric is also not giving very good results

#### Model 2: Dealing with Class Imbalance
- Class Imbalance is a major issue when dealing with classification problems since one class dominates the other class with a large number.
- Keras can be used to deal with class imbalance problems by specifying the weights of the classes.
- Classes with a lesser number of samples can be given more weightage as compared to the dominant class.
![image](https://github.com/Surendraprajapat18/Patient-Survival-Prediction-Deep-Learning/assets/97840357/7a313d1b-620b-4f06-b7ba-43955906f487)

**💡 Conclusion from Model 2:**
    
- The precision score has improved as compared to the previous models.
- The model seems more stable with an acceptable AUC score. 
- Overfitting of the model can also be avoided when after dealing with class imbalance. 

#### Final/Model 3: Using Keras Tuner
- Using Keras Tuner hyperparameter tuning can be done in deep learning models as well.
- In this case, it is always advisable to focus on loss values of both the training and validation data since a model is considered more stable when the loss decreases with each epoch
![image](https://github.com/Surendraprajapat18/Patient-Survival-Prediction-Deep-Learning/assets/97840357/ec5887f9-4699-4f07-b931-dfa212a687b7)

**💡 Conclusion from the Final Model:**

- The validation loss has decreased significantly.
- The precision and recall metrics are improved to some extent.
- The model is more generalized
- learning rate and number of units used are not random but calculated using proper methods. 
