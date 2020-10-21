---

@title[Notes]

@snap[west span-55]
@ul[list-spaced-bullets text-09]
- A Gentle Intro to **```ggplot2```**
@snap[east span-45]
![IMAGE](assets/img/logo.png)
@snapend

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
@snap[west span-55]
@ul[list-spaced-bullets text-09]
> "The simple graph has brought more information to the data analyst’s mind than any other device."
@snap[east span-45]
![IMAGE](assets/img/Tukey.jpg)
@snapend

---

### My personal reasons
* Functional data visualization
	* Wrange data
	* Map data to visual elements
	* Tweak scales, guides, axis, labels, theme
	* Easy to reason about how data drives visualization
	* Easy to iterate
	* Easy to be consistent

---

## What are we getting into?

---
@snap[east span-45]
![IMAGE](assets/img/hex-ggplot2.png)
@snapend
@snap[south span-100]
ggplot2 as a lovely package for data visualisation
@snapend
---
@snapend

@snap[west span-100]
@ul[list-spaced-bullets text-09]
- is a huge package: tons of functions....but it's very well organized
@snap[east span-100]
![IMAGE](assets/img/hex-ggplot2.png)
@snapend
---

- You will know _where_ and _what_ to look for
@snap[east span-100]
![IMAGE](assets/img/poppins-bag.gif)
@snapend

---
- Build complex and customized plots from data in a dataframe
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
@[1-2](You can step-and-ZOOM into fenced-code blocks, source files, and Github GIST.)
@[3,4, zoom-13](Using GitPitch live code presenting with optional annotations.)
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
@[1](You can step-and-ZOOM into fenced-code blocks, source files, and Github GIST.)
@[2-3, zoom-13](Using GitPitch live code presenting with optional annotations.)
@snapend


---

@snap[north-east span-100 text-pink text-06]
Let your code do the talking!
@snapend

```r zoom-18
# This is the correct syntax for adding layers
interviews_plot + 
geom_point()

# This will not add the new layer and will return an error message
interviews_plot
+ geom_point()
```

@snap[south span-100 text-gray text-08]
@[1-2](You can step-and-ZOOM into fenced-code blocks, source files, and Github GIST.)
@[2-3, zoom-13](Using GitPitch live code presenting with optional annotations.)
@snapend

---


---?image=assets/img/code.jpg&opacity=60&position=left&size=45% 100%

@snap[east span-50 text-center]
## Now It's **Your** Turn
@snapend

@snap[south-east span-50 text-center text-06]
[Download GitPitch Desktop @fa[external-link]](https://gitpitch.com/docs/getting-started/tutorial/)
@snapend

