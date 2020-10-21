---
### A reward for all the hard work
@title[Notes]

@snap[east span-50]
![IMAGE](assets/img/hard-work.png)
@snapend

@snap[north-east span-100 text-pink text-06]
Slides and code here

---
## What will you learn today?

---
@title[Add A Little Imagination]

@snap[north-west span-50 text-center]
#### You'll know how to:
@snapend

@snap[west span-55]
@ul[list-spaced-bullets text-09]
- Produce scatter plots, boxplots using ```ggplot2```. </br>
- Describe properly the entire process to create visualisation in R. </br>
- Build complex and customized plots from data in a dataframe. </br>
@ulend
@snapend

@snap[east span-45]
![IMAGE](assets/img/objectives.gif)
@snapend
---

## Why is it Important?

---

> "The simple graph has brought more information to the data analyst’s mind than any other device. - **John Tukey**"
@ulend
![IMAGE](assets/img/Tukey.jpg)
@snapend

---
### IMHO....
* **Functional** data visualization
	1. Wrange data
	2. Map data to visual elements
	3. Tweak scales, guides, axis, labels, theme
* Easy to **reason** about how data drives visualization
* Easy to **iterate**
* Easy to be **consistent**
@snap[north-east span-100 text-pink text-06]
Why is it important?
---

## What are we getting into?

---
@snap[east span-50]
![IMAGE](assets/img/hex-ggplot2.png)
@snapend
@snap[south span-100]
**ggplot2** as a lovely package for **data visualisation**
@snapend
---
@snap[east span-50]
![IMAGE](assets/img/hex-ggplot2.png)
@snapend
@snap[south span-100]
Tons of arguments but very well organized
@snapend
---
---

You will know **where** and **what** to look for
@ulend
![IMAGE](assets/img/poppins-bag.gif)
@snapend

---
and build complex and customized plots from data in a dataframe
@ulend
![IMAGE](assets/img/poppins-bag-kids.gif)
@snapend
---
@snap[north-east span-100 text-pink text-06]
Let your code do the talking!
@snapend

```r zoom-18
# install necessary packages
library(tidyverse)
# import data inputs
interviews_plotting <- read_csv("data_output/interviews_plotting.csv")
```

@snap[south span-100 text-gray text-08]
@[1-2](You can start insalling the library)
@[3,4, zoom-13](Using today morning dataset)
@snapend


---


@snap[north-east span-100 text-pink text-06]
Getting started with ```ggplot2```
@snapend

```r zoom-18
<DATA> %>%
    ggplot(aes(<MAPPINGS>)) +
    <GEOM_FUNCTION>()
```

@snap[south span-100 text-gray text-08]
@[1](Inputs before pipe operators)
@[2-3, zoom-13](Specific arguments for ggplot)
@snapend


---

@snap[north-east span-100 text-pink text-06]
Examples of what will you achieve to make today in R!
@snapend

```r zoom-18
# my first plot with x and y variables
interviews_plotting %>%
ggplot(aes(x = no_membrs, y = number_items)) +
geom_point()
```
@ulend
![IMAGE](assets/img/graph2.png)
@snapend
---

@snap[east span-50 text-center]
## Now It's **Your** Turn
@snapend

@snap[south-east span-50 text-center text-06]
[Download GitPitch Desktop @fa[external-link]](https://gitpitch.com/docs/getting-started/tutorial/)
@snapend

---