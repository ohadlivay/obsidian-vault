automatically combine two schemas using machine learning techniques (predict mappings)

to do so we need to create a matrix sized $N_{schema_{a} Xschema_{b}}$
and populate it with confidence (or probability) 

second matchers is to to zero out any score under some threshold.

next step, change to 0,1  matrix.  then use F1/sensitivity/specificity (?)
to evaluate the algorithm, we need ground truths. 
(confusion matrix). 