# 🏃‍♀️ Fitbit Activity Data Analysis

## 📋 Overview

This project explores and analyzes physical activity data collected from Fitbit users over several days. The goal was to understand daily behavior patterns, compare activity levels across days, and apply clustering techniques to identify user profiles based on their physical activity.

The dataset contains **940 daily records** and includes metrics such as step count, active minutes (segmented by intensity), distances, and calories burned.

---

## 📊 Dataset Information

- **Number of entries:** 940 (daily activity logs)
- **Features:**  
  - `TotalSteps`, `TotalDistance`, `VeryActiveMinutes`, `FairlyActiveMinutes`, `LightlyActiveMinutes`, `SedentaryMinutes`  
  - Distance covered by activity type  
  - `Calories`, `ActivityDate`, `Day` (weekday)  
  - `Id` to identify users

No missing values were detected.

---

## 🧪 Exploratory Data Analysis

### 1. **Total Steps vs Calories**
A positive correlation was observed between the number of steps and calories burned, as expected. Users who walk more tend to burn more calories.

### 2. **Minutes by Activity Category**
Minutes spent were broken down into:
- **Very active**
- **Fairly active**
- **Lightly active**
- **Sedentary**


### 3. **Activity Minutes by Day of the Week**


### 4. **Sedentary Minutes by Day**


### 5. **Calories Burned by Day**


### 6. **Correlation between distances and active minutes**

---

## 🤖 Clustering Analysis (K-Means)

### Objective:
To group users based on their **distance covered** and **activity levels** using unsupervised learning.

### Method:
1. Aggregated data **by user ID**, calculating mean values of:
   - Distances (total, active types)
   - Minutes by activity intensity
   - Calories burned
2. **Standardized** the features
3. Applied **K-Means Clustering** with `k=4`
4. Used **PCA** for 2D visualization of user clusters

### Results:

| Cluster | Activity Level       | Description |
|---------|----------------------|-------------|
| 3       | Very Active          | Long distances, high intensity, very high calories burned |
| 1       | Moderately Active    | Fairly regular activity with a mix of intensities |
| 2       | Lightly Active       | Mostly light activity, fewer intense minutes |
| 0       | Sedentary            | Low distance, low calories, minimal active minutes |

### PCA Visualization:

A scatter plot (2D PCA projection) was generated to visualize user distribution across clusters.

---

## 🔎 Case Study: Users from the Most Active Cluster

Cluster 3 consisted of **only two users**, with very high daily activity:

| ID          | Average Steps | Calories | Very Active Minutes |
|-------------|---------------|----------|---------------------|
| 8053475328  | 14,763        | 2,946    | 85.2                |
| 8877689391  | 16,040        | 3,420    | 66.1                |

**Insights:**
- One user walked more and burned more calories.
- The other had fewer steps but more intense activity (higher very active minutes).
- Indicates different but equally active lifestyles: one favors intensity, the other duration.

---

## 📌 Conclusion

This analysis highlighted:
- Daily and weekly patterns in physical activity
- Strong relationships between steps, activity minutes, and calories
- Distinct user profiles via clustering (from sedentary to very active)
- Real-world behavioral insights through concrete user examples

---

## 📁 Technologies Used

- **Python**
- **Pandas, NumPy**
- **Scikit-learn (PCA, KMeans)**
- **Plotly Express, Seaborn, Matplotlib**

---

## 🧠 Possible Improvements

- Incorporate sleep or heart rate data if available
- Cluster based on time series activity trends instead of averages
- Predict health outcomes (e.g., calorie targets or goal achievement)

---

## 📂 Data Source

Fitbit Fitness Tracker Data (public dataset, typically from [Kaggle](https://www.kaggle.com/datasets/arashnic/fitbit))

---
