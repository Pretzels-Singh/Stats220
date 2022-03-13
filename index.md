# Yahallo Everyone

**Welcome To My Stats 220 Repo!** 

## About me
I am a Second Year University Of Auckland student studing a Bachelors of Computer Science and Statistics.

**My Hobbies Include:**
- Anime
- Pokemon
- Memes
- Gaming

## *Memes!!!*
I Love browsing memes in my spare time therefore decided to make on of my very own.
Below is a meme I made using the R package [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).

![](my_meme.png)

My Inspiration/ Ideas for the Meme:

1. The Yamero Cat Meme was one of my Inpirations.
2. I also took Inspiration from a Gru meme as Shown below and decided to combine the two.
![](https://i.kym-cdn.com/photos/images/newsfeed/001/349/947/2e9.jpg)

The meme Ive made is new/original as it uses a combination of two memes to make something unique and funny.

Below IvE Attached the code which i used to make the meme.
```{r}
#Importing All Cat Photos
library(magick)

glass_cat <- image_read("https://external-preview.redd.it/iISr4C0thtIsbRoLvvWJsB1SQtYiHgJloI46g1V_iRE.png?format=pjpg&auto=webp&s=95ad3aa0e0a6c1048aaf2720db639506e0b07e6b") %>%
  image_scale(300)

sad_cat <- image_read("https://i.kym-cdn.com/photos/images/newsfeed/001/878/329/dfa.jpg") %>%
  image_scale(300)

phone_cat <- image_read("https://preview.redd.it/lnxhrzx6swq61.jpg?auto=webp&s=b0d58c5eb5be5d31c2b5bd2846731851bf9ce633") %>%
  image_scale(300)

thinking_cat <- image_read("https://i.pinimg.com/474x/5e/ac/be/5eacbe33059cfefb574279c7f4db986d.jpg") %>%
  image_scale(300)


#First Row  
first_text <- image_blank(width = 300, 
                          height = 400, 
                          color = "#000000") %>%
  image_annotate(text = "Intiates\nStats 220\nAssignment",
                 color = "#FFFFFF",
                 size = 30,
                 font = "Impact",
                 gravity = "center")
#2nd Row
second_text <- image_blank(width = 300, 
                         height = 400, 
                         color = "#000000") %>%
  image_annotate(text = "Looks At\nMemes For\nIdeas",
                 color = "#FFFFFF",
                 size = 30,
                 font = "Impact",
                 gravity = "center")
#3rd Row
third_text <- image_blank(width = 300, 
                       height = 300, 
                       color = "#000000") %>%
  image_annotate(text = "Opens\nTik Tok ",
                 color = "#FFFFFF",
                 size = 30,
                 font = "Impact",
                 gravity = "center")

#4th Row
last_text <- image_blank(width = 300, 
                       height = 300, 
                       color = "#000000") %>%
  image_annotate(text = "Due Date\nis in\nOne Hour",
                 color = "#FFFFFF",
                 size = 30,
                 font = "Impact",
                 gravity = "center")

#Assigning The Image To Cat
first_row <- c(glass_cat, first_text) %>%
  image_append()

second_row <- c(thinking_cat, second_text) %>%
  image_append()

third_row <- c(phone_cat, third_text) %>%
  image_append()

fourth_row <- c(sad_cat, last_text) %>%
  image_append()

c(first_row, second_row, third_row, fourth_row) %>%
  image_append(stack = TRUE)

```
