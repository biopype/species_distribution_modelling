# Biodiversity Conservation of *Asystasia gangetica* Using Species Distribution Modeling

## Introduction
*Asystasia gangetica*, commonly known as Chinese violet or Genghis primrose, is a perennial ground cover plant belonging to the family Acanthaceae. It is renowned for its blue, purple, and violet-shaped flowers. In addition to its ornamental value, Chinese violet provides various ecological benefits, such as preventing soil erosion, improving soil fertility, and aiding pollination through bees and butterflies.

![pexels-ngochuy-5775202](https://github.com/user-attachments/assets/b7d70b98-8cc3-4cac-bc5c-1ec45ed29c48) 
**Fig 1. Purple-white flowers of *Asystasia gangetica***

Despite its resilience, the increasing threats of climate change, deforestation, habitat destruction, and urbanization pose serious risks to its population. Conserving *Asystasia gangetica* is crucial for maintaining biodiversity and sustaining ecosystem stability. By employing advanced technology, precise tools can identify and protect its habitats.

This project developed a Species Distribution Model (SDM) to predict habitat suitability for *Asystasia gangetica* by integrating species occurrence data and 19 environmental variables. Combining predictive modeling with spatial analysis, this project aims to enhance conservation strategies by highlighting key habitat areas and evaluating the broader ecological impacts of conserving this species.

## Objectives
- Mapping the geographic distribution of *Asystasia gangetica*.
- Identifying significant environmental factors influencing habitat suitability.
- Building a predictive model to aid in conservation planning.

## Model Overview
Our SDM utilizes a random forest model and environmental datasets (occurrence data and bioclimatic variables) to predict regions favorable for *Asystasia gangetica*. Spatial mapping was integrated to achieve the objectives and map the species' distribution.

## Methodology

### 1. Data Collection and Cleaning
Species occurrence data was obtained from the Global Biodiversity Information Facility (GBIF). The dataset contained 11,044 entries with coordinates and occurrence status (present or absent) from various locations worldwide. Data preprocessing involved:
- Removing missing coordinates, duplicates, and unnecessary columns.
- Validating coordinate ranges: latitude (-90 to 90) and longitude (-180 to 80).

The preprocessed dataset included the following columns: `GBIFID`, `species`, `latitude`, `longitude`, and `occurrence status`.

### 2. Plotting Occurrence Data
To visualize the distribution of *Asystasia gangetica*, the species' occurrences were mapped. The map revealed a concentration of the species in southern India, Vietnam, and Mexico.

![image](https://github.com/user-attachments/assets/77ca5a58-5fc9-47bc-8771-a07dd990b4ab)

**Fig 2. Occurrence of the species around the world**

### 3. Environmental Data Integration
High-resolution GeoTIFF files for bioclimatic data were downloaded from the WorldClim database. The dataset included 19 bioclimatic variables derived from monthly temperature and rainfall values, crucial for species distribution modeling. These variables are:

| Code  | Description                                          |
|-------|------------------------------------------------------|
| BIO1  | Annual Mean Temperature                             |
| BIO2  | Mean Diurnal Range (Mean of monthly (max temp - min temp)) |
| BIO3  | Isothermality (BIO2/BIO7) (×100)                    |
| BIO4  | Temperature Seasonality (standard deviation ×100)   |
| BIO5  | Max Temperature of Warmest Month                    |
| BIO6  | Min Temperature of Coldest Month                    |
| BIO7  | Temperature Annual Range (BIO5-BIO6)                |
| BIO8  | Mean Temperature of Wettest Quarter                 |
| BIO9  | Mean Temperature of Driest Quarter                  |
| BIO10 | Mean Temperature of Warmest Quarter                 |
| BIO11 | Mean Temperature of Coldest Quarter                 |
| BIO12 | Annual Precipitation                                |
| BIO13 | Precipitation of Wettest Month                      |
| BIO14 | Precipitation of Driest Month                       |
| BIO15 | Precipitation Seasonality (Coefficient of Variation)|
| BIO16 | Precipitation of Wettest Quarter                    |
| BIO17 | Precipitation of Driest Quarter                     |
| BIO18 | Precipitation of Warmest Quarter                    |
| BIO19 | Precipitation of Coldest Quarter                    |

### 4. Summary Statistics
Statistical analysis was performed for the 19 bioclimatic variables corresponding to the species' occurrence points. Key metrics included mean, minimum, maximum, and standard deviation:

| Variable | Mean      | Min       | Max       | Std Dev   |
|----------|-----------|-----------|-----------|-----------|
| BIO1     | 21.99     | 11.22     | 30.28     | 4.22      |
| BIO2     | 28.98     | 20.73     | 43.41     | 3.13      |
| BIO3     | 24.56     | 16.08     | 34.55     | 2.72      |
| BIO12    | 395.61    | 0.00      | 1986.00   | 225.14    |

### 5. Correlation Analysis and Multicollinearity Assessment
Pearson correlation analysis identified variables with high correlation, such as BIO4 and BIO18 (correlation score of +1). 

![image](https://github.com/user-attachments/assets/11b7f4e8-6a39-4602-ba26-7f94cb5eec09)
**Fig 3. Correlation matrix for the bioclimatic variables**

Variance Inflation Factor (VIF) revealed the highest multicollinearity in BIO14.

![image](https://github.com/user-attachments/assets/2161fb2a-0558-49db-a706-10667a387826)
**Fig 4. Variance Inflation Factor**

### 6. Key Variables
Key variables were identified based on correlation and VIF:
- BIO1: Annual Mean Temperature
- BIO12: Annual Precipitation
- BIO16: Precipitation of Wettest Quarter

### 7. Predictive Model Development
A random forest model was trained using bioclimatic variables and species occurrence data to predict habitat suitability. Model performance metrics included accuracy, AUC-ROC score, and confusion matrix.

### 8. Habitat Suitability Mapping
The model's predictions were visualized through a habitat suitability map, with occurrence points overlaid for validation.

## Key Results and Analysis

### 1. Model Performance
- **Accuracy**: 0.872
- **ROC-AUC**: 0.86  
The model effectively distinguished suitable from unsuitable habitats, with potential for improvement in minimizing false positives.

![image](https://github.com/user-attachments/assets/66206202-60c7-4c22-8d7c-1623d87afcc2)
**Fig 5. ROC-AUC to assess the model performance**

### 2. Habitat Suitability Map
![image](https://github.com/user-attachments/assets/ff5ad4df-e787-4e09-bd88-79551773721b)

![image](https://github.com/user-attachments/assets/4b187c7a-c94c-409a-a469-77ed5c5a5c02)

- **Yellow Regions**: High suitability, aligning with occurrence points.
- **Purple Regions**: Low suitability, suggesting areas where the species is unlikely to thrive.
- Outliers suggest data limitations or species adaptability.
The map provides spatial validation of the model, demonstrating accurate predictions of Asystasia gangetica’s preferred habitats. Insights into adaptability and environmental outliers can guide further research and model refinement.

## Applications for Biodiversity Conservation
The SDM provides actionable insights for the conservation of Asystasia gangetica. This model efficiently highlights areas that should be targeted to protect the species. Conservation efforts such as habitat protection and restoration should be directed towards high-suitability regions highlighted in the map.

## Conclusion
We have mapped the geographic distribution of Asystasia gangetica around the world and identified key environmental variables responsible for the survival of species. The Species Distribution Model for Asystasia gangetica combines accuracy (ROC AUC = 0.86) and habitat suitability map to serve as a vital tool for biodiversity conservation. By identifying critical habitats and ecological drivers, the model empowers targeted conservation actions that not only safeguard Asystasia gangetica but also support ecosystem resilience and global biodiversity goals. Collaborative efforts in sustainability, community engagement, and policy-making will ensure the long-term survival of this iconic species.

## Future Directions
1. Study genetic diversity to refine conservation planning.
2. Model co-existing species to promote ecosystem-wide preservation.
3. Align efforts with international biodiversity initiatives (e.g., CBD, UN SDG 15).
