╔════════════════════════════════════════════════╗

║ WWII WEATHER ANALYSIS & TEMPERATURE PREDICTION ║

╚════════════════════════════════════════════════╝

✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦

  KEY FEATURES                             
  
✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦✦

✔ Merged 2 historical datasets (weather + stations)

✔ Processed 100K+ records with Pandas

✔ Engineered location features using Regex 

✔ Compared ML models: 47.55% vs 96.20% R² 

✔ Built interactive temperature map with Folium    

▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄

  TOP PERFORMERS 
  
▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀

  MODEL                ACCURACY    SPEED      
  
══════════════════════════════════════════════



  Random Forest ★★★    96.20%      Moderate (38s)

██████████████████████████████████████████████

  CODE HIGHLIGHTS
  
██████████████████████████████████████████████

[ DATA MERGE ]

wea = pd.merge(weather, stations, 

               left_on='STA', right_on='WBAN')

[ COORD PROCESSING ]

wea['lat_dir'] = wea['LAT'].str.extract(r'(\d+)([NS])')[1]

[ RANDOM FOREST ]

model = RandomForestRegressor(n_estimators=100)

model.fit(X_train, y_train)

■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■

  GET STARTED                             
  
■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■



Clone repository:

   git clone https://github.com/yourrepo/ww2-weather

 Run analysis:
 
   python analyze_weather.py

♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡

  SUPPORT & FEEDBACK  
  
♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡♡

First Kaggle project! ★彡  

→ Found issues? Open GitHub ticket  

→ Like it? Upvote on Kaggle: [[shortened.link](https://www.kaggle.com/code/mostafaelmenwary/tempera)]  

→ Questions? Email: mostafaelmenwary@gmail.com
