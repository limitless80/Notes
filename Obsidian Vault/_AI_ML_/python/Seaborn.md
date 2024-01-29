Behind the scenes, seaborn uses matplotlib to draw its plots.
```python
# Import seaborn
import seaborn as sns

# Basic lineplot visualization graph
sns.lineplot(data=df, x='x', y='y',color='',hue='z')

# Apply the default theme
sns.set_theme()
#used to change the themes of the plots

# Load an example dataset(its random)
tips = sns.load_dataset("tips")

#Basic catplot
catplot seaborn.catplot(data=df,x='x',y='y',hue='z', col='z',color='balck?',kind='count')  #col is used for spliting the graph  

#scatterplot
sns.scatterplot(data=df, x='x', y='y',color='',hue='z')

#boxplot
sns.boxplot(data=df, x='x', y='y',color='',hue='z')

#histplot
sns.histplot(data=df,x='x',color)

#boxplot
sns.barplot(data=df, x='x', y='y',color='',hue='z')



```
### List of plots
- lineplot
![](https://i.imgur.com/gKcH4Xv.png)

- barplot
![](https://i.imgur.com/U2hq4ZP.png)

- histplot
![](https://i.imgur.com/Km10BOV.png)

- boxplot
![](https://i.imgur.com/lh1r0d4.png)

- scatterplot
![](https://i.imgur.com/0gqgug2.png)

- catplot
![](https://i.imgur.com/BPFY1bf.png)

- relplot
![](https://i.imgur.com/RkMNH95.png)
![](https://i.imgur.com/VhgsybI.png)
