# 📺 YouTube Adview Prediction

## 📌 Project Overview
This project was developed as part of my Internship, where the goal was to predict the number of **YouTube adviews** a video will receive based on other video metrics such as views, likes, dislikes, comments, published date, duration, and category.  

YouTube advertisers pay content creators based on adviews and clicks. By building a reliable prediction model, content creators and marketers can better estimate ad revenue and optimize their strategies.

---

## 📂 Dataset
- The dataset (`train.csv`) contains ~15,000 YouTube videos with the following attributes:
  - **vidid**: Unique video ID  
  - **adview**: Number of adviews (**target variable**)  
  - **views**: Number of unique views  
  - **likes**: Number of likes  
  - **dislikes**: Number of dislikes  
  - **comment**: Number of unique comments  
  - **published**: Video publish date  
  - **duration**: Duration of the video  
  - **category**: Category of the video  

🔗 [Dataset Link](https://drive.google.com/file/d/1Dv-HF10AUUA03AO_cQvar462eXawk0iQ/view?usp=sharing)

---

## 🛠️ Steps Performed
1. **Data Preprocessing & Cleaning**  
   - Removed invalid/missing values  
   - Handled outliers (using IQR)  
   - Converted categorical features into numerical form  
   - Transformed video duration (ISO 8601 → seconds)  

2. **Feature Scaling**  
   - Normalized input features using **MinMaxScaler**  

3. **Model Training**  
   - Implemented multiple regression models:
     - Linear Regression  
     - Support Vector Regressor (SVR)  
     - Decision Tree Regressor  
     - Random Forest Regressor  
     - Artificial Neural Network (ANN with Keras)  

4. **Model Evaluation**  
   - Used metrics: **MAE, MSE, RMSE, and R² Score**  
   - Compared models for generalization and error performance  

---

## 📊 Results
| Model                  | MAE   | MSE   | RMSE  | R² Score |
|-------------------------|-------|-------|-------|----------|
| Linear Regression       | 1.90  | 7.01  | 2.65  | 0.063    |
| SVR                     | 1.66  | 8.25  | 2.87  | -0.102   |
| Decision Tree Regressor | 2.06  | 11.01 | 3.32  | -0.470   |
| Random Forest Regressor | **1.67**  | **5.86**  | **2.42**  | **0.218** ✅ |
| ANN (Keras)             | 1.78  | 6.82  | 2.61  | -0.981   |

👉 **Best Model**: **Random Forest Regressor** performed the best with the lowest RMSE and highest R² score.

---

## 💾 Model Saving
- **Random Forest Regressor** saved as:  
  ```bash
  randomforest_youtubeadview.pkl
