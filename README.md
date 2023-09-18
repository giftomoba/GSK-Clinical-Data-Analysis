# GSK-Clinical-Data-Analysis

## Description
### Context
A new cancer treatment for solid tumours (Miraculon-B) is in development at GSK, data has 
been collected in our recent clinical trial comparing Miraculon-B to the current standard of 
care (i.e., referred to as the ‘control’). The trial has completed, and we need your help to
analyse the data and assess the effectiveness of Miraculon-B. To do this we need you to 
compare Miraculon-B to the standard of care, and explore how different patient sub-groups
may benefit differently from treatment.

## Objective
To examine and analyse the data provided to understand which subgroups of 
patients are benefiting more from the treatment. 

## Task:
- Do patients that take the GSK drug respond more to treatment compared to those in the control group? 
- Can the age, weight or protein concentration of patients predict whether they will respond better to treatment or not?
- Additional Task: Build a Supervised Machine Learning model that can predict whether a patient will respond to a treatment or not.

## Data Description
The dataset clinical-study.csv contains 772 rows (patients) and 7 columns (variables). The 
“response” column is our target showing whether the patient has responded to treatment 
(“Yes”) or not (“No”). In solid tumours, response is based on whether tumours shrink, stay the 
same, or get bigger. If a patient has a tumour that is shrinking, they are classified as 
responder, if they have a tumour that stays the same or gets bigger, they are classified as 
non-responder. Again, please note that this is not real GSK data, but it is similar to the type of 
data and the type of questions we explore every day!
The dataset protein-levels.csv contains 768 rows and 2 columns, The protein_concentration
column shows the concentration of a protein that has been identified as a potential 
predictive biomarker for solid tumours. Predictive cancer biomarkers can be used to identify 
the patients who are or who are not likely to derive benefit from specific therapeutic 
approaches. In this analysis we want to investigate whether the concentration of the protein 
could predict whether the patient will respond or not to treatment. 

## Data Dictionary
- subject_id: Patient ID
- sex: Whether the patient is male or female
- age: The age of the patient 
- weight: The weight of the patient 
- height: The height of the patient
- trt_grp: Whether the patient is receiving the new drug or the standard of care (control)
- Response: Whether the patient responded or not (Yes[Y]/No [N])

### Link to the project jupyter notebook file:
##### Jupyter notebook: https://github.com/giftomoba/GSK-Clinical-Data-Analysis/blob/main/project%20jupyter%20notebook.ipynb
##### Notebook PDF format: https://github.com/giftomoba/GSK-Clinical-Data-Analysis/blob/main/jupyter%20notebook%20pdf.pdf

## Key Patterns Identified:
### 1. Protein Concentration and Response:
![weight protein](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/e1fba93e-c098-4e53-bcc6-92bb7264bf82)
![Cat plot 1](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/46e2adaf-79a2-48e5-899f-c6c3e9cf2ae8)

- Most of the patients with lower Protein levels (approximately below 120 ug/L) in their blood Responded to the treatment across both treatment groups (DRUG & CONTROL).

### 2. Response statistics for DRUG Treatment:
![response DRUG](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/5bd66406-d605-4dcc-8a89-7fcd13223a88)
- Most patients who had the DRUG treatment responded to treatment.
-
![drug cat](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/1c07969b-513d-414c-bc17-c7b8e0c22828)
- Most patient with Positive response had protein levels below 116.
- Most patient with Negative response had protein levels above 116.
- The higher the protein level, the more likely it is for the patient not to respond well.
-
![drug response](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/2bb0ba29-c179-4ee6-9089-aaf918448a35)
- 85% of patients with protein concentrations less than 116 reponded positively to Drug treatment while only 15% showed no response (Perhaps they may have other prevailing health issues).
- 74% of patients whose protein concentration was above 116 showed no response to Drug treatment.
-
![drug gender](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/f1734d1e-d81f-443e-ba4b-e67ca8908de0)
- 51.4% of patients with no response to drug treatment were males while 48.6% were females.


### 3. Response statistics for CONTROL Treatment:
![CONTROL 3](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/1f57f916-8ac8-479e-8455-09d8537a78d0)
- A larger percent (67.8%) of patient who took the CONTROL didn't respond to treatment while less than half of the patients who took the control measure responded well to treatment.

![control cat](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/ccebed1e-5ac0-47ea-8c1e-12db34100202)
- Most patients who responded to the CONTROL treatment had protein concentrations between 90 and 117. Those who didn't respond (67.8%) had protein concentration between 107 and 149.
- 
![control response](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/cdfce282-7cb0-4ba7-ad1b-05168434cb04)
- Over 83% of patients who took CONTROL treatment, with protein concentrations higher than 116, showed no response.
- Overall, most patients did not respond to CONTROL treatment.



## Overall Result From Analysis:
- Patients in treatment group 'DRUG' has an overall positive response while the 'CONTROL' group responded poorly.
- The protein concentration in the blood played a key role in determining the response of a patient in both DRUG and CONTROL treatment groups. 
- Protein Levels of most patients with no response ranges between 112 and 155 ug/L.
- Protein Levels of most patients with positive response ranges between 91 and 116 ug/L.
- Most patients who took the DRUG treatment responded positively
- DRUG: 85% of patients with protein concetration less than 116 ug/L responded positively while ony 15% showed no response.
- DRUG: About 78% of patients with protein levels higher than 116 ug/L showed no response.
- CONTROL: Most patients who showed no response had protein concentration between 107 and 149 ug/L.
- CONTROL: 83.8% of patients above 116 ug/l protein concentration showed no response, with only about 16% responding.
- In summary, the lower the amount of protein concentration in the blood, the better the chances of both treatment groups having a positive response and vice versa.

### RECOMMENDATION:
- Since the drugs performed better overall, it can be taken to the next level in trials, if need be, and more improvement carried out to increase its positive effect on patient.
- Both treatments (drug and control) should only be administered to patients with protein levels less than 107 ug/L for CONTROL treatment and less than 116 ug/L for DRUG treatment. 
- However, since there is a relationsip between the protein levels and the patient's response to treatment, to get the best result and make the treatment effective, patients should be informed or advised to reduce their protein intake, perhaps for few days leading to and after taking the drug. This would also help improve the effect and performance of the drug.
### MODEL PERFORMANCE SUMMARY:
![model2](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/51ef37c5-1aca-486b-805d-c4b19840e9e2)
![model1](https://github.com/giftomoba/GSK-Clinical-Data-Analysis/assets/124467481/8106414b-5af0-41bb-aa1b-1d44bc3fa36c)

- Although Logistic Regression performed well in identifying whether or not a patient responds, it had about 84% recall, which means it has the tendency to misclassify 16% of the patients as responding to treatment, whereas they did not.
- It is highly recommended that the model be improved upon for better performance or more test carried out on patient to determine their response to the treatment.
