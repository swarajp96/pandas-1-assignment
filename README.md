# pandas-1-assignment
pandas 2 assignment
In [4]:
import numpy as np 
import pandas as pd
Import the dataset from this (https://raw.githubusercontent.com/justmarkham/DAT8/master/data/u.user).
In [5]:
df = pd.read_csv('u.user', sep = '|')
Assign it to a variable called users and use the 'user_id' as index
In [17]:
data = pd.read_csv('u.user',sep = '|',index_col = 'user_id')
data
Out[17]:
age	gender	occupation	zip_code
user_id				
1	24	M	technician	85711
2	53	F	other	94043
3	23	M	writer	32067
4	24	M	technician	43537
5	33	F	other	15213
...	...	...	...	...
939	26	F	student	33319
940	32	M	administrator	02215
941	20	M	student	97229
942	48	F	librarian	78209
943	22	M	student	77841
943 rows × 4 columns

See the first 10 and last 10 entries
In [5]:
print(data.head(10))
print(data.tail(10))
   user_id  age gender     occupation zip_code
0        1   24      M     technician    85711
1        2   53      F          other    94043
2        3   23      M         writer    32067
3        4   24      M     technician    43537
4        5   33      F          other    15213
5        6   42      M      executive    98101
6        7   57      M  administrator    91344
7        8   36      M  administrator    05201
8        9   29      M        student    01002
9       10   53      M         lawyer    90703
     user_id  age gender     occupation zip_code
933      934   61      M       engineer    22902
934      935   42      M         doctor    66221
935      936   24      M          other    32789
936      937   48      M       educator    98072
937      938   38      F     technician    55038
938      939   26      F        student    33319
939      940   32      M  administrator    02215
940      941   20      M        student    97229
941      942   48      F      librarian    78209
942      943   22      M        student    77841
What is the number of observations in the dataset?
In [6]:
print('No of Observations :', data.shape[0] )
0
No of Observations : 943
Out[6]:
0
What is the number of columns in the dataset?
In [35]:
print('No of Columns:',data.shape[1])
No of Columns: 5
Print the name of all the columns.
In [36]:
print(data.columns)
Index(['user_id', 'age', 'gender', 'occupation', 'zip_code'], dtype='object')
How is the dataset indexed?
In [18]:
print(data.index)
Int64Index([  1,   2,   3,   4,   5,   6,   7,   8,   9,  10,
            ...
            934, 935, 936, 937, 938, 939, 940, 941, 942, 943],
           dtype='int64', name='user_id', length=943)
What is the data type of each column?
In [42]:
print(data.dtypes)
user_id        int64
age            int64
gender        object
occupation    object
zip_code      object
dtype: object
Print only the occupation column
In [26]:
print(data['occupation'])
0         technician
1              other
2             writer
3         technician
4              other
           ...      
938          student
939    administrator
940          student
941        librarian
942          student
Name: occupation, Length: 943, dtype: object
How many different occupations are in this dataset?
In [55]:
print(data['occupation'].value_counts())
student          196
other            105
educator          95
administrator     79
engineer          67
programmer        66
librarian         51
writer            45
executive         32
scientist         31
artist            28
technician        27
marketing         26
entertainment     18
healthcare        16
retired           14
lawyer            12
salesman          12
none               9
homemaker          7
doctor             7
Name: occupation, dtype: int64
What is the most frequent occupation?
In [7]:
print(data['occupation'].mode())
0    student
dtype: object
DataFrame Info.
In [8]:
print(data.info)
<bound method DataFrame.info of      user_id  age gender     occupation zip_code
0          1   24      M     technician    85711
1          2   53      F          other    94043
2          3   23      M         writer    32067
3          4   24      M     technician    43537
4          5   33      F          other    15213
..       ...  ...    ...            ...      ...
938      939   26      F        student    33319
939      940   32      M  administrator    02215
940      941   20      M        student    97229
941      942   48      F      librarian    78209
942      943   22      M        student    77841

[943 rows x 5 columns]>
Describe all the columns
In [9]:
print(data.describe)
<bound method NDFrame.describe of      user_id  age gender     occupation zip_code
0          1   24      M     technician    85711
1          2   53      F          other    94043
2          3   23      M         writer    32067
3          4   24      M     technician    43537
4          5   33      F          other    15213
..       ...  ...    ...            ...      ...
938      939   26      F        student    33319
939      940   32      M  administrator    02215
940      941   20      M        student    97229
941      942   48      F      librarian    78209
942      943   22      M        student    77841

[943 rows x 5 columns]>
Summarize only the occupation column
In [16]:
print(data['occupation'].describe)
<bound method NDFrame.describe of 0         technician
1              other
2             writer
3         technician
4              other
           ...      
938          student
939    administrator
940          student
941        librarian
942          student
Name: occupation, Length: 943, dtype: object>
What is the mean age of users?
In [17]:
print(data['age'].mean())
34.05196182396607
What is the age with least occurrence?
In [25]:
print(data['age'].min())
7
In [ ]:
