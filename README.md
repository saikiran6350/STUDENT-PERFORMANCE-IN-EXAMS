# STUDENT-PERFORMANCE-IN-EXAMS
#IMPORT PANDAS
#IMPORT NUMPY
import numpy as np
import pandas as pd
#READING DATA FROM CSV FILE
#USE PANDAS READ CSV() METHOD TO READ THE DATA FROM CSV FILE
df = pd.read_csv('D:\exams.csv')
df
gender	race/ethnicity	parental level of education	lunch	test preparation course	math score	reading score	writing score
0	female	group D	some college	standard	completed	59	70	78
1	male	group D	associate's degree	standard	none	96	93	87
2	female	group D	some college	free/reduced	none	57	76	77
3	male	group B	some college	free/reduced	none	70	70	63
4	female	group D	associate's degree	standard	none	83	85	86
...	...	...	...	...	...	...	...	...
995	male	group C	some college	standard	none	77	77	71
996	male	group C	some college	standard	none	80	66	66
997	female	group A	high school	standard	completed	67	86	86
998	male	group E	high school	standard	none	80	72	62
999	male	group D	high school	standard	none	58	47	45
1000 rows × 8 columns

# HEAD() METHOD TO DISPLAY THE FIRST FIVE ROWS OF THE DATA
df.head()
gender	race/ethnicity	parental level of education	lunch	test preparation course	math score	reading score	writing score
0	female	group D	some college	standard	completed	59	70	78
1	male	group D	associate's degree	standard	none	96	93	87
2	female	group D	some college	free/reduced	none	57	76	77
3	male	group B	some college	free/reduced	none	70	70	63
4	female	group D	associate's degree	standard	none	83	85	86
# TAIL() METHOD DISPLAY THE LAST FIVE ROWS FROM THE DATA
df.tail()
gender	race/ethnicity	parental level of education	lunch	test preparation course	math score	reading score	writing score
995	male	group C	some college	standard	none	77	77	71
996	male	group C	some college	standard	none	80	66	66
997	female	group A	high school	standard	completed	67	86	86
998	male	group E	high school	standard	none	80	72	62
999	male	group D	high school	standard	none	58	47	45
# GET THE NUMBER OF OBSERVATIONS AND NUMBER OF COLUMNS AND ROWS OF THE DATA USING THE shape ATTRIBUTE
df.shape
(1000, 8)
# GET THE DATA TYPE OF EACH VARIABLE IN THE DATA USING THE dtype ATTRIBUTE
df.dtypes
gender                         object
race/ethnicity                 object
parental level of education    object
lunch                          object
test preparation course        object
math score                      int64
reading score                   int64
writing score                   int64
dtype: object
# PANDAS info() PRINT THE INFORMATION ABOUT THE SHAPE,DATA TYPE AND NULL VALUES UN THE DATA
df.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 1000 entries, 0 to 999
Data columns (total 8 columns):
 #   Column                       Non-Null Count  Dtype 
---  ------                       --------------  ----- 
 0   gender                       1000 non-null   object
 1   race/ethnicity               1000 non-null   object
 2   parental level of education  1000 non-null   object
 3   lunch                        1000 non-null   object
 4   test preparation course      1000 non-null   object
 5   math score                   1000 non-null   int64 
 6   reading score                1000 non-null   int64 
 7   writing score                1000 non-null   int64 
dtypes: int64(3), object(5)
memory usage: 62.6+ KB
# INDEXING
# PRINT THE 99ND ROW FROM THE DATA BY USING THE iloc[] METHOD
df.iloc[98]
gender                               female
race/ethnicity                      group B
parental level of education     high school
lunch                          free/reduced
test preparation course           completed
math score                               75
reading score                            90
writing score                            95
Name: 98, dtype: object
# PRINT THE ANY FOUR ROWS USING iloc[] METHOD
df.iloc[99:103]
gender	race/ethnicity	parental level of education	lunch	test preparation course	math score	reading score	writing score
99	male	group C	some college	free/reduced	none	83	62	64
100	male	group D	high school	standard	none	88	72	74
101	male	group C	bachelor's degree	standard	none	59	50	53
102	male	group D	associate's degree	standard	none	74	69	63
#PRINT FIRST TWO COLUMNS BY USING THE POSITION OF THE COLUMNS
df.iloc[:,:2]
gender	race/ethnicity
0	female	group D
1	male	group D
2	female	group D
3	male	group B
4	female	group D
...	...	...
995	male	group C
996	male	group C
997	female	group A
998	male	group E
999	male	group D
1000 rows × 2 columns

# PRINT THE MALES DATA
 
# SORTING THE ROW math score IN THE ASCENDING ORDER

df.sort_values('math score')
gender	race/ethnicity	parental level of education	lunch	test preparation course	math score	reading score	writing score
586	female	group D	high school	free/reduced	none	15	39	40
228	male	group C	high school	free/reduced	none	20	25	15
480	female	group C	high school	standard	none	21	30	26
72	female	group C	some high school	standard	none	23	33	33
693	female	group C	high school	free/reduced	none	24	48	46
...	...	...	...	...	...	...	...	...
213	male	group B	master's degree	standard	none	100	90	88
85	male	group D	master's degree	standard	none	100	97	91
580	male	group E	some college	standard	completed	100	89	86
857	male	group E	bachelor's degree	standard	completed	100	100	100
203	male	group E	high school	standard	none	100	91	85
1000 rows × 8 columns

# PRINT THE writing score IN DESCENDING ORDER

df.sort_values('writing score',ascending=False)
gender	race/ethnicity	parental level of education	lunch	test preparation course	math score	reading score	writing score
292	female	group E	associate's degree	standard	none	96	93	100
732	female	group D	associate's degree	standard	completed	82	95	100
857	male	group E	bachelor's degree	standard	completed	100	100	100
835	female	group D	bachelor's degree	standard	completed	83	100	100
566	male	group D	associate's degree	standard	completed	99	100	100
...	...	...	...	...	...	...	...	...
762	male	group C	high school	free/reduced	none	34	37	27
480	female	group C	high school	standard	none	21	30	26
982	male	group C	some high school	standard	none	28	27	23
376	male	group C	high school	standard	none	31	27	19
228	male	group C	high school	free/reduced	none	20	25	15
1000 rows × 8 columns

# SORT THE TWO COLUMNS 

df.sort_values(['writing score','reading score'])
gender	race/ethnicity	parental level of education	lunch	test preparation course	math score	reading score	writing score
228	male	group C	high school	free/reduced	none	20	25	15
376	male	group C	high school	standard	none	31	27	19
982	male	group C	some high school	standard	none	28	27	23
480	female	group C	high school	standard	none	21	30	26
762	male	group C	high school	free/reduced	none	34	37	27
...	...	...	...	...	...	...	...	...
389	female	group D	high school	standard	completed	91	100	100
566	male	group D	associate's degree	standard	completed	99	100	100
835	female	group D	bachelor's degree	standard	completed	83	100	100
857	male	group E	bachelor's degree	standard	completed	100	100	100
899	female	group B	some college	standard	completed	92	100	100
1000 rows × 8 columns

# SOTING INDEX
df['math score']=df['math score']
df['math score']
0      59
1      96
2      57
3      70
4      83
       ..
995    77
996    80
997    67
998    80
999    58
Name: math score, Length: 1000, dtype: int64
# DATA CLEANING PROCESS
# CHECKING THE NULL VALUES IN DATA SET
df.isnull().sum()
gender                         0
race/ethnicity                 0
parental level of education    0
lunch                          0
test preparation course        0
math score                     0
reading score                  0
writing score                  0
dtype: int64
