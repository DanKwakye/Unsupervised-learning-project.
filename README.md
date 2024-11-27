# Unsupervised-learning-project.
In the project, I used unsupervised learnning to determine categories of countries that need help
### Objective:  
HELP International has raised $10 million to support global development efforts. The CEO now faces the critical task of identifying countries in dire need of aid to allocate these funds effectively. As a data scientist, your role is to analyze socio-economic and health-related factors to categorize countries based on their overall development levels. Your findings will guide the CEO's decisions on where the aid will have the most significant impact.  

---

### Exploratory Data Analysis (EDA):  
The dataset consists of 167 rows and 10 features, mostly numerical (integer or float). The only text feature, **"country"**, identifies each nation uniquely but does not add value to the modeling process. However, it will be useful for exploratory analysis.  

#### Key Observations:  
1. **Feature Skewness:**  
   Variables like child mortality (*child_mort*), exports, imports, income, inflation, and GDP per capita (*gdpp*) have significant differences between their 75th percentile and maximum values, indicating right-skewed distributions.  
   
2. **Outliers:**  
   Boxplots reveal notable outliers in features such as child mortality, exports, imports, income, and GDP per capita. These outliers reflect inherent differences between countries rather than data errors, so they will not be removed.  

3. **Relationships Between Features:**  
   - Higher GDP correlates with lower child mortality rates.  
   - Exports and income show a positive relationship with GDP.  
   - Fertility rate (*total_fer*) is positively related to child mortality but negatively related to life expectancy (*life_expec*).  
   - Life expectancy and child mortality are inversely related.  

#### Cluster Patterns:  
Preliminary graphs reveal two distinct clusters:  
1. African and South Asian countries.  
2. The rest of the world.  

---

### Principal Component Analysis (PCA):  
PCA was used for dimensionality reduction while preserving the variation in the data. Based on the variance ratio, we considered three to five clusters for analysis.  

---

### K-Means Clustering:  
K-Means clustering was applied to group countries into categories. This algorithm divides countries into clusters based on similarity, minimizing the distance between each country and its cluster centroid.  

The **Elbow Method** was used to determine the optimal number of clusters. Three clusters were selected, as they provided a good balance between simplicity and explanatory power.  

#### Clusters Identified:  
1. **Countries Needing Immediate Help:**  
   Includes most African nations, along with countries like Pakistan, Afghanistan, Iraq, Yemen, and Laos. These 47 nations exhibit low GDP, high child mortality, and other pressing socio-economic challenges.  

2. **Countries That Might Need Help:**  
   Many Asian countries fall into this category, indicating moderate development and some need for support.  

3. **Countries Not Needing Help:**  
   Developed nations such as the U.S., Canada, Australia, and most European countries fall here, showing strong economic and health indicators.  

---

### Conclusion:  
This analysis categorizes countries based on socio-economic and health indicators:  
- The **"Help Needed"** group includes countries requiring urgent aid, primarily in Africa and parts of Asia.  
- The **"Might Need Help"** group includes countries with moderate needs, mainly in Asia.  
- Developed nations are in the **"No Help Needed"** category.  

These findings provide a clear roadmap for HELP International to prioritize its funding, ensuring the $10 million raised is directed where it is needed most.
