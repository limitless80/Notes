```python
#import of the module
import matplotlib.pyplot as plt
#get the line plot with title,graph info(title),label(x,y), rotation of (x,y)
plt.plot('x-value','y-value', color=['b','g','r','c','m','y','k','w',], label='legend')
plt.title('Title name')
plt.xlabel('xlabel')
plt.ylabel('ylabel')
plt.xticks(rotation=0,45,90)
plt.yticks(rotation=0,45,90)
plt.legend()
#get figure size
plt.figure(figsize=(float(width), float(height), facecolor=color)
#get black background
plt.style.use(['dark_background'])
#get multiple plots
fig(axi1,axi1) = plt.subplots(1, 2, figsize=(width,height))
#assign axi1 and axi2 to different plot
axi1 = plt.plot()
axi2 = plt.plot()
#get subplots based on rown and columns
plots = plt.subplot(nrows=int( ), ncols=int( ), figsize=(width,height))
#get values filled between two values
plt.fill_between(first_point, second_point, density(first_point), color='color',alpha=int('color intensity from 0-1.0'))
#get bar plot
plt.bar(x, height)
#get scatter plot
plt.scatter(x, height)
#get histogram plot
plt.hist(x, height)
#get boxplot
plt.boxplot(values)i
#get grid
plt.grid()
#get plot shown in function
plt.show()
```
labels
![](https://i.imgur.com/BPT2iXU.png)
colors
![](https://i.imgur.com/nTWee46.png)

