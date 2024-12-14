# Biodiversity Conservation of *Asystasia gangetica* Using Species Distribution Modeling

Comprehensive report: [species_distribution_modelling/report.md]

## Introduction
*Asystasia gangetica* (Chinese violet) is a perennial ground cover plant valued for its ecological benefits, including preventing soil erosion, improving soil fertility, and aiding pollination. However, threats such as climate change and habitat destruction jeopardize its survival. This project employs Species Distribution Modeling (SDM) to predict suitable habitats and aid conservation efforts.

## Objectives
- Map geographic distribution of *A. gangetica*.
- Identify key environmental factors influencing habitat suitability.
- Build a predictive model for conservation planning.

## Methodology
1. **Data Collection & Cleaning**:  
   Species occurrence data (from GBIF) with 11,044 entries and 19 bioclimatic variables (from WorldClim) were processed and validated.
   
2. **Visualization**:  
   Occurrence data plotted on maps showed distribution concentrated in southern India, Vietnam, and Mexico.
   
3. **Key Variables**:  
   Identified using correlation analysis and VIF:
   - BIO1: Annual Mean Temperature  
   - BIO12: Annual Precipitation  
   - BIO16: Precipitation of Wettest Quarter  

4. **Model Development**:  
   A random forest model trained on species occurrence and bioclimatic data achieved an accuracy of 87.2% (ROC AUC = 0.86). 

5. **Habitat Suitability Mapping**:  
   High-suitability areas were visualized, with occurrence points overlaid for validation.

## Key Results
- Model achieved high accuracy and ROC performance, validating its reliability.
- Habitat suitability map identified areas for conservation, aligning with occurrence points. Some discrepancies indicate potential data limitations or species adaptability.

![image](https://github.com/user-attachments/assets/0bb268cb-1272-4c9f-8853-3de1fea1c1b7)

## Applications
This SDM highlights critical habitats for *A. gangetica*, guiding conservation strategies like habitat protection and restoration to ensure species survival and ecosystem resilience.

## Conclusion
The SDM effectively identifies suitable habitats and ecological drivers for *A. gangetica*, supporting biodiversity conservation goals. Collaborative efforts in sustainability, community engagement, and policy-making can ensure its long-term survival.

## Future Directions
- Study genetic diversity and adaptability for better conservation planning.
- Model co-existing species to promote ecosystem-wide preservation.
- Align efforts with international biodiversity programs (CBD, SDG 15).

bioclimatic variable data (bio_10m): (WorldClim)[https://www.worldclim.org/data/worldclim21.html]
