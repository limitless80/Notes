Behind the scenes, seaborn uses matplotlib to draw its plots.
```python
# Import seaborn
import seaborn as sns

# Basic lineplot visualization graph
sns.lineplot(data=df, x='x', y='y')

# Apply the default theme
sns.set_theme()
#used to change the themes of the plots

# Load an example dataset(its random)
tips = sns.load_dataset("tips")

#Lineplot




```
### List of plots
- lineplot
- barplot
- histplot
- boxplot
- scatterplot
- catplot
- relplot