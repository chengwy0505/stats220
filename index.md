# Hi!
*Welcome to my test website!*
## About me
I am a data sciense student at **the University of Auckland**. I love movies and music. My favorite music is hiphop.
## Meme (First attempt)
Below is a meme I made using the R package for first time [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).
![my_meme](https://github.com/chengwy0505/stats220/blob/main/my_meme.png)
## My meme is original:
These are the two meme that I often use, representing sad and happy feelings. I put the two meme together to create a different sense of contrast, and attached text to express the mood of using meme. So this is my original meme
## A short summary of my inspiration for my meme is: 
1.It's a meme I use all the time

2.The texts of meme are what I think when I use this meme.
## Provide the R code I used to make the meme! 

'''

library(magick)

#picture one

Smile_praise <- image_read("https://www.meme-arsenal.com/memes/fdc79d5250a627ce8357fdf0e3a9f79b.jpg") %>%
  image_scale(300)

#picture two

Crying_hug <- image_read("https://www.meme-arsenal.com/memes/12710ab699636c88c7f4d570284fd0cb.jpg") %>%
  image_scale(300)

#text_square one

meme_text1 <- image_blank(width = 500, height = 500, color = "#99ff33") %>%
  image_annotate(text = " Smile and say you are great!", color = "#ff471a", size = 30, font = "Segoe Print", gravity = "center")

#text_square one

meme_text2 <- image_blank(width = 500, height = 500, color = "#99ff33") %>%
  image_annotate(text = "Can you hug me when I am sad?", color = "#ff471a", size = 30, font = "Segoe Print", gravity = "center")

first_row <- c(Smile_praise, meme_text1) %>%
  image_append()

second_row <- c(Crying_hug, meme_text2) %>%
  image_append()

meme <- c(first_row, second_row) %>%
  image_append(stack = TRUE)

print(meme)

image_write(meme, "my_meme.png")

'''
