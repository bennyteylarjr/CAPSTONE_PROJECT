# CAPSTONE_PROJECT
IBM DATA SCIENCE CAPSTONE PROJECT

EXECUTIVE SUMMARY
This research aims to identify the factors contributing to a successful rocket landing for SpaceX. By leveraging public data and machine learning models, we predict the likelihood of first-stage landings, which directly impacts launch costs. The study includes data collection through APIs and web scraping, data wrangling, exploratory data analysis (EDA), and predictive modeling using logistic regression, support vector machine (SVM), decision tree, and K-nearest neighbor (KNN) algorithms. Our findings highlight that launch success has improved over time, with certain launch sites and orbits showing higher success rates. Among the models, the decision tree slightly outperformed the others.

INTRODUCTION
SpaceX, a pioneering company in the space industry, has revolutionized space travel by making it more affordable. One of their key innovations is the reuse of the first stage of their Falcon 9 rocket, which significantly reduces launch costs. This study aims to predict the likelihood of first-stage landings using historical launch data. Understanding the factors that influence landing success can help SpaceX and other space companies optimize their operations and reduce costs.

Objectives
- Determine how payload mass, launch site, number of flights, and orbits affect first-stage landing success.
- Analyze the rate of successful landings over time.
- Identify the best predictive model for successful landing outcomes.

METHODOLOGY

Data Collection - API
- SpaceX API: Data on rocket launches was collected using the SpaceX REST API.
  - The response was decoded using `.json()` and converted to a DataFrame with `.json_normalize()`.
  - Custom functions were used to request detailed launch information, creating a dictionary and converting it to a DataFrame.
  - The dataset was filtered to include only Falcon 9 launches, and missing values for Payload Mass were replaced with the mean.

Data Collection - Web Scraping

- Wikipedia: Falcon 9 launch data was scraped from Wikipedia.
  - A BeautifulSoup object was created from the HTML response.
  - Column names were extracted from the HTML table header, and data was parsed from HTML tables.
  - A dictionary was created from the data and converted to a DataFrame.

Data Wrangling
- Outcomes were converted into binary values: 1 for a successful landing and 0 for an unsuccessful landing.

Exploratory Data Analysis (EDA)
- Visualization: Relationships and comparisons were analyzed using various charts.
- SQL Analysis: Queries were executed to gain deeper insights into the data.

Maps with Folium
- Visualization: Maps were created to visualize launch sites, outcomes, and distances to geographical proximities.

Dashboard with Plotly Dash
- Dashboard Creation: A dashboard was developed to present key metrics.
  - Pie charts displayed successful launches.
  - Scatter plots showed the relationship between Payload Mass and Success Rate by Booster Version.

Predictive Analytics
- A NumPy array was created from the Class column.
- The data was standardized using `StandardScaler`.
- The dataset was split using `train_test_split`.
- `GridSearchCV` with `cv=10` was used for parameter optimization.
- Algorithms applied: logistic regression (`LogisticRegression()`), support vector machine (`SVC()`), decision tree (`DecisionTreeClassifier()`), and K-Nearest Neighbor (`KNeighborsClassifier()`).
- Model accuracy was calculated using `.score()` on the test data.
- Confusion matrices were assessed, and the best model was identified using Jaccard Score, F1 Score, and Accuracy.

RESULTS

Exploratory Data Analysis
- Launch success has improved over time.
- KSC LC-39A has the highest success rate among landing sites.
- Orbits ES-L1, GEO, HEO, and SSO have a 100% success rate.

Predictive Analytics
- All models performed similarly on the test set, with the decision tree model slightly outperforming others.

DISCUSSION
The analysis revealed several key factors that contribute to successful landings. The proximity of launch sites to the equator provides a natural boost due to the Earth's rotational speed, aiding in fuel and booster efficiency. Coastal locations also facilitate logistics and safety measures. Over time, launch success has increased, highlighting SpaceX's improvements in technology and operations. Specific launch sites, such as KSC LC-39A, demonstrated higher success rates, particularly for launches under 5,500 kg. Certain orbits also showed consistent success.

CONCLUSION
- Model Performance: The decision tree model slightly outperformed other models in predicting landing success.
- Success Trends: Launch success has increased over time, with certain sites and payload ranges showing higher success rates.
- Orbit Success: Orbits ES-L1, GEO, HEO, and SSO have demonstrated a 100% success rate.

By identifying these factors, SpaceX can further optimize its operations and reduce costs, making space travel more accessible and sustainable.

APPENDIX

Launch Sites
- Cape Canaveral Air Force Station (CCAFS)
- Kennedy Space Center (KSC) LC-39A
- Vandenberg Air Force Base (VAFB)
- Boca Chica, Texas
- Cape Canaveral LC-40
