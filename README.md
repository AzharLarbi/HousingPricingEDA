# Exploratory Data Analysis on US Home Prices
This repository contains code for performing exploratory data analysis (EDA) on factors influencing home prices across the US. The primary purpose of this analysis is to understand the relationships between various economic indicators and home prices. The dataset used for this analysis can be found on Kaggle: Factors Influence the Home Prices Across US.

# Data Sources
demand_data.csv
supply_data.csv
# Tools Used
Pandas: For data manipulation and analysis.
Matplotlib: For data visualization.
Seaborn: For advanced data visualization.
# Code Overview
# Data Preparation
1. Reading Data:
```
dem_df = pd.read_csv('demand_data.csv')
sup_df = pd.read_csv('supply_data.csv')
```
2. Converting to Datetime:
```
dem_df['DATE'] = pd.to_datetime(dem_df['DATE'])
sup_df['Period'] = pd.to_datetime(sup_df['Period'], format='%d-%m-%Y').dt.strftime('%Y-%m-%d')
sup_df.rename(columns={'Period': 'DATE'}, inplace=True)
sup_df['DATE'] = pd.to_datetime(sup_df['DATE'])
```
3. Merging Data:
```
df = pd.merge(dem_df, sup_df)
df.to_csv('supp_dem.csv', index=False)
```
4. Extracting Date Components:
