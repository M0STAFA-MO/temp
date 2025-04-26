markdown
# 🌦️ WWII Weather Analysis & Temperature Prediction  
**Machine Learning Pipeline from Raw Data to 96.2% Accuracy**  
[![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-blue)](https://kaggle.com/yourprofile)  
[![Python 3.8](https://img.shields.io/badge/Python-3.8%2B-green)](https://www.python.org/)  
[![License](https://img.shields.io/badge/License-MIT-orange)](LICENSE)  

---

### 📚 **Full Workflow in One View**  

**1. Data Fusion & Cleaning**  
Merged station locations with weather measurements using Pandas:  
```python  
wea = pd.merge(  
    pd.read_csv('Summary of Weather.csv'),  
    pd.read_csv('Weather Station Locations.csv'),  
    left_on='STA', right_on='WBAN', how='left'  
)  
Parsed latitude/longitude directions (N/S/E/W) with regex:

python
wea['lat_direction'] = wea['LAT'].str.extract(r'(\d+)([A-Za-z]+)')[1]  
2. Smart Preprocessing

Converted categories to numbers using LabelEncoder:

python
wea['NAME'] = LabelEncoder().fit_transform(wea['NAME'])  
Handled outliers in precipitation data:

python
wea['Precip'] = pd.to_numeric(wea['Precip'], errors='coerce')  
3. Machine Learning Showdown
Trained and compared two models:

Model	R² Score	Training Time
Linear Regression	47.55%	2.1s
Random Forest	96.20%	38.5s
Code snippet for the winning model:

python
model = RandomForestRegressor(n_estimators=100, random_state=42)  
model.fit(X_train, y_train)  
print(f"R²: {r2_score(y_test, model.predict(X_test))*100:.2f}%")  
4. Geo-Insights Visualization
Created interactive maps with Folium to explore temperature patterns:

python
m = folium.Map(location=[0,0], zoom_start=2)  
for _, row in data_grouped.iterrows():  
    folium.CircleMarker(  
        location=[row['Latitude'], row['Longitude']],  
        radius=row['MeanTemp']/5,  
        popup=f"Temp: {row['MeanTemp']:.1f}°C",  
        color='#ff0000'  
    ).add_to(m)  
m.save('temperature_map.html')  
🚀 How to Replicate
Install dependencies:

bash
pip install pandas scikit-learn folium  
Clone & run:

bash
git clone https://github.com/yourusername/ww2-weather-analysis  
cd ww2-weather-analysis  
python main.py  
💬 Your Feedback Matters!
This is my first Kaggle notebook! 🙌

👉 Notice an error? Open a GitHub issue!

💡 Improvement idea? Comment on Kaggle!

❤️ Found it useful? Upvote & share!

Connect:
Kaggle
GitHub


---

### Key Features:  
1. **Seamless Flow** ➡️ No section breaks, natural progression  
2. **Code-Result Pairing** 💻 Each code block followed by its purpose  
3. **Visual Dividers** ✨ Lines/emojis代替标题  
4. **Mobile-Ready** 📱 Uniform left alignment  
5. **Action-Oriented** 🎯 Clear "How to Replicate" steps  
