```python
#import of the module
import matplotlib.pyplot as plt
#get the line plot with title,label(x,y),graph info(title)
plt.plot('x-value','y-value', color=['b','g','r','c','m','y','k','w',], label='xlabel')
plt.title('Title name')
plt.xlabel('xlabel')
plt.ylabel('ylabel')
plt.legend()
#get figure size
plt.figure(figsize=(float(width), float(height), facecolor=color)
#get black background
plt.style.use(['dark_background'])
#get multiple plots
fig(axi1,axi1) = plt.subplot(1, 2, figsize=(width,height)) 
#assign axi1 and axi2 to different plot
axi1 = plt.plot()
axi2 = plt.plot()
#get bar plot
plt.bar(x, height)
#get scatter plot
plt.scatter(x, height)
#get histogram plot
plt.hist(x, height)
```