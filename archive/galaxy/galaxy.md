

```python
from random import randint
from statistics import mean, median
```


```python
from matplotlib import pyplot, rcParams
```


```python
def vectors(minAmount, maxAmount):
    v = []
    means = []
    medians = []
    y = []
    yDiv = randint(-5, 5)
    if yDiv == 0:
        yDiv = randint(1, 5) if randint(1, 2) == 1 else randint(-5, -1)

    yDivChanges = randint(1, 2) == 1

    for i in range(randint(minAmount, maxAmount)):
        v.append([])
        for j in range(randint(3, 1000)):
            v[i].append(randint(-100, 100))

        means.append(mean(v[i]))
        medians.append(median(v[i]))

        if yDivChanges:
            yDiv += randint(-5, 5)
            if yDiv == 0:
                yDiv = 1

        y.append((max(v[i]) + min(v[i])) / yDiv)
    
    return means, medians, y

def generate_galaxy():
    markers = ["x", ".", "o"]
    colours = ["xkcd:baby blue", "xkcd:sky blue", "xkcd:sunshine yellow", "xkcd:light yellow", "xkcd:cyan", "xkcd:white"]
    
    means, medians, y = vectors(5000, 10000)
    
    meansOrMedians = "means" if randint(1, 100) <= 30 else "medians"
    x = means if meansOrMedians == "means" else medians

    rcParams["figure.figsize"] = 10, 10
    pyplot.scatter(x, y, marker=markers[randint(0, len(markers) - 1)], color=colours[randint(0, len(colours) - 1)])
    
    if randint(1, 100) <= 40:
        means, medians, y = vectors(3, 3333)
        if meansOrMedians == "means":
            x = means if randint(1, 100) <= 80 else medians
        else:
            x = medians if randint(1, 100) <= 80 else means
        pyplot.scatter(x, y, marker=markers[randint(0, len(markers) - 1)], color=colours[randint(0, len(colours) - 1)])
            
    
    pyplot.xticks([], [])
    pyplot.yticks([], [])
    pyplot.gca().set_facecolor("black")
    pyplot.show()

for i in range(5):
    generate_galaxy()
```


![png](output_2_0.png)



![png](output_2_1.png)



![png](output_2_2.png)



![png](output_2_3.png)



![png](output_2_4.png)



```python
for i in range(25):
    generate_galaxy()
```


![png](output_3_0.png)



![png](output_3_1.png)



![png](output_3_2.png)



![png](output_3_3.png)



![png](output_3_4.png)



![png](output_3_5.png)



![png](output_3_6.png)



![png](output_3_7.png)



![png](output_3_8.png)



![png](output_3_9.png)



![png](output_3_10.png)



![png](output_3_11.png)



![png](output_3_12.png)



![png](output_3_13.png)



![png](output_3_14.png)



![png](output_3_15.png)



![png](output_3_16.png)



![png](output_3_17.png)



![png](output_3_18.png)



![png](output_3_19.png)



![png](output_3_20.png)



![png](output_3_21.png)



![png](output_3_22.png)



![png](output_3_23.png)



![png](output_3_24.png)



```python
for i in range(25):
    generate_galaxy()
```


![png](output_4_0.png)



![png](output_4_1.png)



![png](output_4_2.png)



![png](output_4_3.png)



![png](output_4_4.png)



![png](output_4_5.png)



![png](output_4_6.png)



![png](output_4_7.png)



![png](output_4_8.png)



![png](output_4_9.png)



![png](output_4_10.png)



![png](output_4_11.png)



![png](output_4_12.png)



![png](output_4_13.png)



![png](output_4_14.png)



![png](output_4_15.png)



![png](output_4_16.png)



![png](output_4_17.png)



![png](output_4_18.png)



![png](output_4_19.png)



![png](output_4_20.png)



![png](output_4_21.png)



![png](output_4_22.png)



![png](output_4_23.png)



![png](output_4_24.png)

