WORLD WAR II WEATHER ANALYSIS & TEMPERATURE PREDICTION
A machine learning project analyzing historical weather patterns to predict mean temperatures using WWII-era data.

KEY FEATURES:

Merged weather measurements with station location data

Processed coordinates (latitude/longitude) using regex

Converted categorical data via Label Encoding

Compared Linear Regression vs. Random Forest models

Interactive geographic visualization of temperatures

TOP RESULTS:

Linear Regression achieved 47.55% R² accuracy

Random Forest achieved 96.20% R² accuracy (best model)

CORE CODE SNIPPETS:

Data Merging:
wea = pd.merge(weather_data, station_locations, left_on='STA', right_on='WBAN')

Coordinate Processing:
wea['lat_direction'] = wea['LAT'].str.extract(r'(\d+)([A-Za-z]+)')[1]

Model Training:
model = RandomForestRegressor(n_estimators=100, random_state=42)
model.fit(X_train, y_train)

HOW TO RUN:

Install requirements: pip install pandas scikit-learn folium

Clone repo: git clone https://github.com/yourusername/ww2-weather

Execute: python main.py

FEEDBACK WELCOME!
This is my first Kaggle notebook - suggestions welcome!
Like this work? Please upvote on Kaggle: [kaggle.com/yournotebook]
Full code: [github.com/yourrepo]
