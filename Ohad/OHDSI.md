[source](https://www.youtube.com/watch?v=7-T9a8I1uN8)
Obseravation Health Data Sciences And Informatics. 
A collaborative effort to bring health data to the community in order to improve health decisions.
## Community
around 4K collaborators spanning 80 countries, 21 time zones, 6 continents, all part of 1 community.
## OMOP
OHDSI is the successor of OMOP (Observational Medical Outcomes Partnership). 
## Example study
The 2020 OHDSI hypertension study compared **chlorthalidone** and **hydrochlorothiazide** to evaluate clinical guideline preferences. Analyzing 730,000 patients across three US databases, researchers used "Target Trial Emulation" with 60,000 patient characteristics and negative controls to eliminate bias.

The study found **no difference in effectiveness** regarding cardiovascular outcomes. However, chlorthalidone showed **significantly higher risks** of hypokalemia and renal dysfunction. These findings were later validated by the $10 million VA "DCP" randomized trial. This success proved that OHDSI’s standardized, open-science approach produces reliable, high-impact clinical evidence faster and more cost-effectively than traditional experimental methods.
## OHDSI Tools
PLP
Mortality
PLE
Drug Safety
# Data Standardization
What can you standardize?
Data structure: table, fields, data types
Data content: vocabulary to 'codify' clinial domains
Data semantics: conventions about meaning
Cohort (population) definitions
... and more
![[Pasted image 20251219072201.png]]

# Open world VS Closed world
00:43:28
In Open World, we assume;
* what we know, we know.
* what we don't know, we don't know.
In Closed world, we assume:
* What we know, we know.
* What we don't know, **is false**

Bottom line:
To use patient data, we have to use closed world assumptions!! lots of data we will encounter will not be under this assumption.

Some data types often violate CWA: negative records (record showing patient DOES NOT have asthma for example), free text, survey data. any datatype where we can't answer  what null is equal to.

# Methodologic Research
# Clinical Evidence Generation
