### Get a list of unique values across multiple columns 

library(dplyr)
iris %>% 
  select(Sepal.Width, Species) %>% 
  t %>% c %>% unique
  
 [1] "3.5"        "setosa"     "3.0"        "3.2"        "3.1"       
 [6] "3.6"        "3.9"        "3.4"        "2.9"        "3.7"       
[11] "4.0"        "4.4"        "3.8"        "3.3"        "4.1"       
[16] "4.2"        "2.3"        "versicolor" "2.8"        "2.4"       
[21] "2.7"        "2.0"        "2.2"        "2.5"        "2.6"       
[26] "virginica" 

See this [StackOverflow answer](https://stackoverflow.com/questions/7790732/unique-for-more-than-one-variable)
