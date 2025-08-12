# Solar-Energy-Production-Analysis-
This project was created during Data Analysis Competition by ITS. The project was aim to find strategies to enhance the effectiveness of energy production from solar panels at a particular site, focusing on the fourth quarter of 2017. This evaluation will involve analyzing the area's various environmental and weather conditions to create forecasting models that estimate solar output and enhance energy efficiency.

# Preparation
<img width="2366" height="623" alt="image" src="https://github.com/user-attachments/assets/d91aa57f-ec6d-4a38-94a5-04daa555c92b" />

- Environments data (Solar Irradiance) was merged into 1 file; every separate day, month, and time was merged into single Timestamp column
- Each of DHI, DNI, and GHI along with their respective clearsky counterparts have approximately 7.92% missing value. Handling less than 10% missing values was taken.
- Weather and Train data has no missing values
<img width="1420" height="198" alt="image" src="https://github.com/user-attachments/assets/1692e5fe-0ad9-4456-9460-3f7a6c614fb0" />
- Environments and weather data merged according to the Timestamp
<img width="1202" height="763" alt="image" src="https://github.com/user-attachments/assets/a3bb784a-8965-47bc-b085-3e74e6b2a3fe" />
- Before merging the environmental conditions with train data, cheking and handling for un-matching Timestamp was conducted to ensure none duplicated data

# Modeling
<img width="1153" height="767" alt="image" src="https://github.com/user-attachments/assets/91d092e9-b157-4836-b8ec-c52b1aac202c" />
- These features were chosen because they capture sunlight availability (GHI, DHI, DNI) and environmental factors (wind speed, temperature, pressure) that directly affect solar panel efficiency and energy output. Automatically identifies the target variable. It then splits the data into training (80%) and testing (20%) sets, trains a Random Forest Regressor, makes predictions, and evaluates performance using RMSE to measure how accurately the model predicts solar energy output.
- Before evaluate with test data, we scales the input features using StandardScaler, and performs hyperparameter tuning for two models: Random Forest Regressor and XGBoost Regressor.

<img width="1365" height="734" alt="image" src="https://github.com/user-attachments/assets/c5286f65-93d1-4b91-bcf7-b5cce383451d" />
<img width="1156" height="179" alt="image" src="https://github.com/user-attachments/assets/17cafaf4-ed94-46dc-964f-16a312d246d8" />
- Random Forest achieved an RMSE of 0.2126, meaning predictions deviate from the actual values by ~0.21 units on average.
- XGBoost achieved a similar RMSE of 0.2139, only slightly higher, indicating comparable performance.

<img width="606" height="621" alt="image" src="https://github.com/user-attachments/assets/ce2d0926-2bee-4160-89ba-be27d2b5bd2b" />
- The predictive model estimates % Baseline solar output with moderate accuracy (RMSE ≈ 0.21). While many predictions align closely with actual performance, certain periods show notable deviations, potentially linked to weather variability or sensor inaccuracies.

# Recommendations
- Inspect panels when actual output is below predictions.
- Calibrate sensors regularly.
- Plan maintenance around low-output forecasts.


Link to full demonstration: https://colab.research.google.com/drive/193WVKUfCFPhbdpEMPJD5E9ModjzhMN92?usp=sharing 
