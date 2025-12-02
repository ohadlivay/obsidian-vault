# Sequence Modeling
predict or generate a sequence of data points - like text, weather, stocks. 
each data point is *dependant* on the previous one!
use-cases: speech recognition, image captioning, subtitle generator and translation. 
## Types of sequence modeling problems
Many - many outputs with dependance between them (like time or position in sentence).
Many to one - predict one output. like sentiment classification.
One to many - predict a sequence based on a single input. like image captioning - we get 1 image and we predict. 
Many-to-many -  like translation.

Neurons with recurrence

parallel? 
multi-modality? 

upgrades: LSTM, GRU..

problems: have a hard time handling long history. 