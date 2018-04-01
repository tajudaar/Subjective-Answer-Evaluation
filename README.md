# Subjective-Answer-Evaluation
IDEA is to evalaute the subjective/descriptive answers from the model answer is provided.
Basically for the first attempt I have ceated a Python Flask App which is hosted at https://pure-woodland-16548.herokuapp.com where student can give there answer.
Currently It has 3 general OOPS related questions. After submiting the data goes to Firebase.
And when the "givVal.py" script is executed it will evaluate and store in Firebase DB the answers of each question based on ML algorithm that I have implemented.

At the core NB classifier is working. With 21 recorde available in it.

(This dataset is manually written by me after observing some real answersheets evalauted by university Professors.)

(I know its very very very small dataset but still atleast read the complete documentation you'll get to know what it is! :) )

(herer is that Datase-> https://github.com/im-minion/Subjective-Answer-Evaluation/blob/master/Modules/finaldataset.csv)


For doing this evaluation I have used 3 Parameters 
##### 1.Keywords
##### 2.Grammar
##### 3.Qusetion Specific Things (QST)

The dataset have 4 attributes viz. "keywords", "grammar", "qst"(Qusetion Specific Things) and "class".
"class" is the attribute that ML algo. will predict after providing values of remaining 3 attributes.

So,
the values of "keywords" and "qst" attributes defined as :(1-excellent,2-verygood,3-good,4-ok,5-poor,6-verypoor)

the values of "grammer" attribute defined as: (0-improper,1-proper) and finally

the value of "class" ranges from 1 to 9. 


##### 1.Keywords
Evaluation of Keywords based Cosine Similarity of "student's/user's answer" with "model answer".

Firstly texts (i.e. student's and model answer) converted into vectors. And from these two vectors the Cosine similarity is Calculated.

Now this gives value from 0 to 1. this is converted into numeric form (i.e. 0 to 100). And then keywords will get the value from 1-6


##### 2.Grammar
For this number of grammatical mistakes taken into consideration.

For this API provided by https://textgears.com is used. Thanks for that :) .

##### 3.Qusetion Specific Things (QST)
Fuzzy Logic is used to give the value of qst.

(FuzzyWuzzy libraray from https://github.com/seatgeek/fuzzywuzzy this is used. Thanks for that :) ).


(PS: I am begineer in ML and this is my first own project. For Any Suggestions please let me know here vaibhavminiyar@gmail.com )
