# Look more Repositories
[GitHub](https://github.com/G00L00/stats220)

## Quiclook the result
![Study_VS_Planning](https://github.com/G00L00/stats220/blob/main/study%20VS%20planting.png?raw=true) 

# Materials
1. package.magick()
   * **image_read** **image_write**
   * **c(), image_blank(), image_read(), image_annotate(), image_append()**
2. images from the web
   * [widecombo church](https://widcombe.church/)
   * [worldatlas](https://www.worldatlas.com/)
## What is the image to say
*Learning is very similar to growing plants, when we start learning it is like planting seeds and 
when we practice what we have learned it is like really watering. These two are the things that 
a plant must go through from seed to fruit, learning is the same, the lack of any step can not be considered a good learning*
   
# Code
```r
library(magick)
seed <- image_read("https://widcombe.church/wp-content/uploads/2021/03/planting-seeds.jpg") %>%
  image_scale(800)
growth <- image_read("https://www.worldatlas.com/r/w960-q80/upload/2b/38/98/shutterstock-244220368.jpg")%>%
  image_scale(800)



seed_text <- image_blank(width=800,height = 600, color ="#90EE90")%>%
  image_annotate(text = "Learning = planting",
                 color = "#FFF8DC",
                 size = 70,
                 font = "Impact",
                 gravity = "center")

growth_text <- image_blank(width=800,height = 600, color = "#90EE90")%>%
  image_annotate(text = "Practice = watering",
                 color = "#FFF8DC",
                 size = 70,
                 font = "Impact",
                 gravity = "center")



seed_out <- c(seed,seed_text)%>% 
  image_append()
growth_out <- c(growth,growth_text)%>% 
  image_append()


c(seed_out,growth_out) %>%
  image_append(stack =TRUE)
all_all <- image_read("http://localhost:20593/session/preview.jpeg?viewer_pane=1&capabilities=1&host=http%3A%2F%2F127.0.0.1%3A41192")
image_write(all_all,path = "study VS planting.png",format = "png")
```
