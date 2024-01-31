```python
#import pandas
import pandas as pd

#Series is a 1d labeled array
series = pd.Series([1,2,3,4,strings,other_data_types]) #don't forget that 'S' is capital

#Dataframe is a 2d array in the form of a table
df = pd.DataFrame(series,index=[1,2,3,4,5])

#convert a Series to a Dataframe
df = series.to_frame()

#Reading data
df.head(n) #list the first n files; defaults to 5
df.tail(n) #list the last n files; defaults to 5

df.index #lists the index
df.columns #list the cloumns
df.info #lists the column name and their datatypes

#basic Stastics
#center tendencies
df['column'].mean()  or  df.column.mean()  #mean
df['column'].median()  or  df.column.median() #median
df['column'].mode()  or  df.column.mode() #mode

df['column'].var()  or  df.column.var() #variance
df['column'].std()  or  df.column.std() #Standard-deviation
df['column'].max()-df['column'].min() #Range
df['column'].min() #minimum
df['column'].max() #maximum

#shape of the data
#tells which side the data skews towards [negetive means that it is left skewed][positive means that the data is right skewed]
df['column'].skew() 
#kurt tell the hight of the peak and legenth of the tails of the data 
df['column'].kurt()

df.groupby['column'] #used to do stastics by grouping up similar rows in a given column




```

[[Stastics]]