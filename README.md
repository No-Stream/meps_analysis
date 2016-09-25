##Brief Summary

I've specified quite a bit in the .ipynb file, but here's a brief outline of what I've done.

I started by cleaning the data - we have tons of duplicates. I also eliminated some variables that seemed to hold little value, at least for initial analyses.  

I then joined our prescription info to our demographics. This way, we can run our analyses, which require prescription info. I converted several columns to forms that can be interpreted by learning algorithms (e.g. False/True instead of "Yes"/"No").  

Then I could start answering your questions. Figuring out the most common prescriptions was simple enough - I just iterated through the diagnoses and found the most common drug for each diagnosis.  

I thought that interpretation of the second question was slightly subjective, but I interpreted it as, essentially, asking for the highest specificity of a drug as a "test" for a disease. I calculated and graphed these.  

For the model, I chose diabetes, since it was reasonably common and had a few very diagnostic medicines (e.g. Metformin). I then trained a logistic regression to get a feel for the effects of different variables and then a random forest as an initial model.  

Of course, without encoding the drug names, the model isn't very good, so I did that, and model performance improved a bit. I also tried one-hot encoding some drug names, but this didn't boost model performance.  

As a bonus, I trained an xgboost model, evaluated its AUC-ROC curve, and tweaked its decision threshold to produce a higher recall for diabetes-positive persons.