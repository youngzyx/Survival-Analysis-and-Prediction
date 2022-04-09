

As part of our coursework at USF, we are supposed to complete nine months'practicum. We were always interested in applying Deep Learning to solve problems in the healthcare space which led me to our internship at UCSF.

### Project 1 Survival Analysis:

#### Background

Clinicians use DS - GPA(Diagnosis-specific Graded Prognostic Assessment) model to segment patients by cancer severity to better inform the treatment decision they need to take. However, there were a few problems with this model. 

1) patients lived far longer than predicted by the model. 
2) Additionally, there was a significant overlap in the patient survival times between the GPA classes.

We needed to apply the DS GPA model to our dataset and develop a new DS-GPA model to replace the existing one.

#### Solution:
We had data on 8k patients that had developed metastatic brain cancer and their demographic information( age, sex etc) and their disease presentation metrics( such as the size of the tumor)

We used a decision tree classifier to segment the patients by survival times and Kaplan Meier curve curves to check the separation between the classes.


### Project 2 Predicting tumor growth:

Problem:

Due to the side effects associated with cancer treatment, clinicians need to understand which patients to treat more aggressively relative to others  
which is where our model comes in. It predicts the tumor's probability to grow based on its initial presentation. 

The Dataset:

We had 8500 MRI images of brain tumors and additional features like tumor size and density 
for the first part; we used the 8k images to predict disease progression. We started by training an Alex Net, which was not complex enough to detect the patterns within the tumor. We then moved on to implementing a ResNet, and we are currently working on improving its performance.

We also plan to include additional features like tumor size and density to better the model performance.
