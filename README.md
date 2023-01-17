![sharon-mccutcheon--iaHr12PVQg-unsplash](https://user-images.githubusercontent.com/8728172/212955595-7b1b1c6e-e404-4338-95a7-f37ac8a96a25.jpg)

**Problem** : 
Nurses are responsible for maintaining care of pregnant folks during their CTG. They are also burdened with reading and interpreting the CTG which can get in the way of maintaining care of the folks in their charge.

**Proposed Solution** : 
Train an algorithm to read the CTG and provide insights towards early detection of pathological CTG scans so nurses can do what they're best at: Patient Care, and health outcomes are improved.

***Data*** This dataset contains 2126 records of features extracted from Cardiotocogram exams, which were then classified by three expert obstetricians into 3 classes:

Normal

Suspect

Pathological
 

**METHODS:**

![Machines Ranked by Recall in Pathological Class](https://user-images.githubusercontent.com/8728172/177601974-8fa36b56-9ced-4cdf-bee1-08fc522ad3bd.png)

I tested iterations of Logistic Regression, KNN, Support Vector Machines, and Random Forest, with and without gridsearch crossvalidations, both as is and inside a One Vs All wrapper. I made recall of the Pathological class my target metric. 

**RESULTS:**

I have two final models to propose: 

<img width="358" alt="OVR_RF_test_gridsearch_cm" src="https://user-images.githubusercontent.com/8728172/177602326-4ff11151-35c6-4f36-9374-2b334096b687.png">

The above model had a 90% precision of the Pathological class with a 92% Recall in the Pathological class, using all features. 

By using SHAP to reduce dimensionality I was able to produce another model for roll out. 
![SHAP Importances](https://user-images.githubusercontent.com/8728172/177602822-08ee88bd-fb7a-49ea-8c2a-9ad5d0613800.png)



<img width="358" alt="Final_model_test_grid" src="https://user-images.githubusercontent.com/8728172/177602338-22a2355b-e7d3-4890-ab3f-238f63116e84.png">

The above model had a 91% precision of the Pathological class with a 88% Recall in the Pathological class, using a subset of features. 

I'm proposing to do A/B testing on the two models to see which has the most utility. 


**FUTURE WORK: **
1) Retune Models

2) Reorganize Data Collection Methods
 
3) Iterative test Dimensionailty Reduction
 
3) Secondary test for Suspected Diagnoses
 
Recommendations:

Birthing centers, hospitals and women's health centers should be on the look out for some early indicators:
 
1) A low histogram median.
 
2) A low short term variability.
 
3) A high prolonged decelerations.
 
These signs all point to fast tracking that patient for further diagnostic testing.
 
These are the simplest-to-interpret, most expressive features in my research targeting Pathological Diagnoses.
 
For data collection:
 
1) We can reduce the amount of data we are collecting for the purposes of this model, as proven by the model with reduced dimensions.
 
2) We can be more specific in our data collection towards lethal prenatel diagnoses specifically.

***SOURCES***
I'll be using Cardiotocogram information from CITATION: https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification.

**Further Reading**: https://onlinelibrary.wiley.com/doi/10.1002/1520-6661(200009/10)9:5%3C311::AID-MFM12%3E3.0.CO;2-9

This data was published in 2000, by Marques de SÃ¡, J.P., Biomedical Engineering Institute, Porto, Portugal. Bernardes, J., Faculty of Medicine, University of Porto, Portugal. Ayres de Campos, D., Faculty of Medicine, University of Porto, Portugal.
This is an appropriate data source for this problem/solution because it has a mix of Cardiotocogram information that range from normal to suspected diagnosis to pathological diagnosis.


​​CITATION: https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification

**CITATION** : Dua, D. and Graff, C. (2019). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.


This is a paper by the original collectors of the data about their Machine Learning results.





**REPO NAV:**

--.ipynb_checkpoints

--images

----plots

---------.DS_Store
    
---------Abnormal Short Term Variability.png
    
---------Accelerations.png
    
---------Baseline Value.png
    
---------Fetal Movement.png
    
---------Final_model_test_grid.png
    
---------Histogram Max.png
    
---------Histogram Mean.png
    
---------Histogram Median.png
   
---------Histogram Min.png
   
---------Histogram Mode.png
    
---------Histogram Number Of Peaks.png
    
---------Histogram Number Of Zeroes.png
    
---------Histogram Tendency.png
    
---------Histogram Variance.png
    
---------Histogram Width.png
    
---------Light Decelerations.png
   
---------Machines Ranked by Recall in Pathological Class.png
    
---------Mean Value Of Long Term Variability.png
    
---------Mean Value Of Short Term Variability.png
    
---------OVR_RF_test_gridsearch_cm.png
   
---------Percentage Of Time With Abnormal Long Term Variability.png
    
---------Prolongued Decelerations.png
    
---------SHAP Importances.png
    
---------Severe Decelerations.png
   
---------Target Correlation Barplot.png
    
---------Target Correlation.png
    
---------Uterine Contractions.png
    
---------cdc_mm_by_race.jpeg
 
 
  -- PDFs
  
  --.DS_Store
    
   -- Predicting Pathological Prenatal Diagnoses.pdf
    
   --final_notebook - Jupyter Notebook.pdf
    
   --github.pdf
  
  --.DS_Store
  
  --State-restrictions-on-abortion-map-June-2022-thumbnail.webp
  
  --dan-meyers-f1WMJR8pLqo-unsplash.jpg
  
  --sharon-mccutcheon--iaHr12PVQg-unsplash.jpg
  
  --stephen-andrews-kHAqo7qXoJw-unsplash.jpg
  
--.DS_Store

--Predicting Pathological Prenatal Diagnoses.pdf

--.gitattributes

--README.md

--fetal_health.csv

--final_notebook.ipynb

