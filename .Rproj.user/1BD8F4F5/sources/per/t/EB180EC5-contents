library("tidyverse")
str(surveys)
#to execute this click ctrl and enter

select(surveys,species_id,weight)
#select is variable with surveys, and then columns being species_id
#subset of original data frame

filter(surveys, year==1995)

#only want ID and weight
#add additional pipe ctrl shift m
# Pipe %>% 
surveys %>% 
  filter(year==1995) %>% 
  select(species_id,weight)

#select only the rows with species, weight less than 5, then only select species id, sex and weight
exercise <- surveys %>% 
   filter(weight<5) %>% 
   select(species_id, sex, weight)

#create new column
#mutate(survey, name of new variable)

data_with_kg <- surveys %>% 
  mutate(weight==weight/1000)

surveys %>% 
  mutate(weight_kg==weight_kg/1000,weight_kg==weight*2)

#piping already from the survey data frame to see the first 6 observations
surveys %>% 
  mutate(weight_kg==weight_kg/1000,weight_kg==weight*2) %>% 
  head()

#missing data noted- weight was already missing
#how to select and remove missing data where there is no weight

surveys %>%
  filter(!is.na(weight)) %>% 
  mutate(weight_kg=weight/1000,weight_kg2=weight*2) %>% 
  head()

#split sexes into new variables
#groups data
#remove missing weight
surveys %>% 
  filter(sex=="M" | sex== "F") %>% 
  group_by(sex) %>% 
  summarise(mean_weight= mean(weight,na.rm=TRUE))

#group by two columns

summarise_two <- surveys %>%
  filter(!sex=="") %>% 
  filter(!is.na(weight)) %>% 
  group_by(sex,species_id) %>% 
  summarise(mean_weight=mean(weight))
  

#arrange
surveys %>% 
  filter(!sex=="") %>% 
  count(sex,species) %>% 
  arrange(species,desc(n))

?==  
?