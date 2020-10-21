---

@title[Notes]
---?image=assets/img/logo.png&opacity=60&position=left&size=45% 100%
#### A Gentle Intro to **```ggplot2```**
---?image=assets/img/hex-ggplot2.jpg&opacity=60&position=right&size=45% 100%
@snap[north-west span-50 text-center]

---
@carlosug
Slides and code: github
[c.utrillaguerrero@maastrichtuniversity.nl](c.utrillaguerrero@maastrichtuniversity.nl)
---

#### A Practical workshop to get researchers further down the reproducible research path



---

## Course Material 

[Google Colab Index @fa[external-link]](https://colab.research.google.com/github/MaastrichtU-IDS/global-studies-methods/blob/master/notebooks/Index.ipynb#scrollTo=0gaW4qKEKG06)
@snapend


---

## What is Reproducible Research?

---

![image](assets/img/hex-ggplot2.png&opacity=60&position=right&size=45% 100%)

Source: https://thenib.com

---

## Why is it Important?

---

![image](https://raw.githubusercontent.com/orchid00/ReproducibleResearchThings/gh-pages/assets/img/reproducibility-graphic-online3.jpg)

Source: [Nature doi:10.1038/533452a](https://www.nature.com/news/polopoly_fs/7.36718.1464174471!/image/reproducibility-graphic-online3.jpg_gen/derivatives/landscape_630/reproducibility-graphic-online3.jpg)

---

One of the **core principles** of the scientific process is that **other** scientists are able to **repeat** your experiment and come to the **same conclusion**

---

No one wants their research to be `retracted`

* some data were missing
* untracked version of changes
* mistakes were made
  * true error
  * ecological fallacies
  
---

---

### Help researchers learn to be reproducible researchers
  
---

### Today we are going to learn **9 lessons** to safeguard us against these situations

---

### Let's look at some scenarios....

---

### What if a key person from your lab disappeared one day? 
(e.g. family or personal emergency, no longer contactable)

---

* Could you all continue your work?
* Would you know where all `the data` and other inputs are stored?
* Could you keep running effectively for 1 month?

`1 year?`

---

![image](https://github.com/guereslib/Reproducible-Research-Things/raw/master/images/376c2ff9d8260fa7c1ae4a3468e1bce9.jpg)
Source: [Upturned Microscope](https://theupturnedmicroscope.com/comic/real-vs-movie-scientist-3/)

---

### Let's look at a few tools we can use to protect our research

---

## Documentation
### Naming Conventions
### Folder Structures
### Automation
### Version Control

---

## Step 1 
## Documentation

---
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
If you hanve't done yet!
@snapend

```r zoom-8
interviews_plotting <- interviews %>%
## pivot wider by items_owned
separate_rows(items_owned, sep = ";") %>%
## if there were no items listed, changing NA to no_listed_items
replace_na(list(items_owned = "no_listed_items")) %>%
mutate(items_owned_logical = TRUE) %>%
pivot_wider(names_from = items_owned, 
            values_from = items_owned_logical, 
            values_fill = list(items_owned_logical = FALSE)) %>%
## pivot wider by months_lack_food
separate_rows(months_lack_food, sep = ";") %>%
mutate(months_lack_food_logical = TRUE) %>%
pivot_wider(names_from = months_lack_food, 
            values_from = months_lack_food_logical, 
            values_fill = list(months_lack_food_logical = FALSE)) %>%
## add some summary columns
mutate(number_months_lack_food = rowSums(select(., Jan:May))) %>%
mutate(number_items = rowSums(select(., bicycle:car)))
```
@snapend

---

---

@snap[north-east span-100 text-pink text-06]
Let your code do the talking!
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

---
@title[Notes]
---?image=assets/img/code.jpg&opacity=60&position=right&size=45% 100%
@snap[north-west span-50 text-center]
#### What you have learned:
@snapend

@snap[west span-55]
@ul[list-spaced-bullets text-09]
- Anything you put in ```ggplot()``` can be seen by any geo layers you added
- You can specify **mapping with**  ```aes()```
- The ```+``` sign must be placed at the end of the line of _previous layer_

@ulend
@snapend
---
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

