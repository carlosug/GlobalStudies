# Let's Get **Started**

---

### Add Some Slide Candy

![IMAGE](assets/img/presentation.png)

---?color=linear-gradient(180deg, white 75%, black 25%)
@title[Customize Slide Layout]

@snap[west span-55]
## Customize the Layout
@snapend

@snap[north-east span-45]
![IMAGE](assets/img/presentation.png)
@snapend

@snap[south span-100]
Snap Layouts let you create custom slide designs directly within your markdown.
@snapend

---
@title[Add A Little Imagination]

@snap[north-west span-50 text-center]
#### What will you learn:
@snapend

@snap[west span-55]
@ul[list-spaced-bullets text-09]
- You will create amazing graph
- Using R and R studio
- With a **little support**
- On function specifications
- And build complex and customized plots from data
@ulend
@snapend

@snap[east span-45]
![IMAGE](assets/img/conference.png)
@snapend

@snap[south span-100 bg-black fragment]
@img[shadow](assets/img/conference.png)
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

### Plotting with `ggplot2` 
(e.g. family or personal emergency, no longer contactable)
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

@snap[north-west span-50 text-center]
#### What you have learned:
@snapend

@snap[west span-55]
@ul[list-spaced-bullets text-09]
- Anything you put in ```ggplot()``` can be seen by any geo layers you added
- You can specify **mapping with**  ``àes()``
- The ```+```sign must be placed at the end of the line of _previous_layer
- On function specifications
@ulend
@snapend


@snap[east span-45]
![IMAGE](assets/img/conference.png)
@snapend

@snap[south span-100 bg-black fragment]
@img[shadow](assets/img/conference.png)
@snapend

---
---

@snap[north-east span-100 text-pink text-06]
Let your code do the talking!
@snapend

```r zoom-18
## This is the correct syntax for adding layers
interviews_plot +
    geom_point()

## This will not add the new layer and will return an error message
interviews_plot
+ geom_point()
```

@snap[south span-100 text-gray text-08]
@[1](You can step-and-ZOOM into fenced-code blocks, source files, and Github GIST.)
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

