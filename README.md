# The gardeners' guide to planting the right plant, in the right zone.
### An example set of SQL queries to show proficiency.


### I want to know what types of edible foods I could plant in my garden and when I should plant them.
### Joining tables in order to understand when to plant my garden. 

SELECT  
  plants.Plant_Name as name,
  plants.Plant_Type as type,
  plants.Preferred_Zone as zone,
  plants.Use as use,
  plants.Poisonous as poison,
  native.Time_to_Flower_Days as bloom

FROM 
  `kpolitte.The_Green_Gardener.plants` as plants
    left join `kpolitte.The_Green_Gardener.native` as native on plants.Plant_Name = native.Plant_Name

where 
  plants.Use = "Edible"
  AND plants.Poisonous = "No"

order by plants.Plant_Name




### I want to target foods that are fruits, vegetables, and herbs.

SELECT  
  plants.Plant_Name as name,
  plants.Plant_Type as type,
  plants.Preferred_Zone as zone,
  plants.Use as use,
  plants.Poisonous as poison,
  native.Time_to_Flower_Days as bloom

FROM 
  `kpolitte.The_Green_Gardener.plants` as plants
    left join `kpolitte.The_Green_Gardener.native` as native on plants.Plant_Name = native.Plant_Name

where 
  plants.Plant_Type = "Fruit"  and plants.Use = "Edible" and plants.Poisonous = "No"
  or plants.Plant_Type = "Vegetable" and plants.Use = "Edible" and plants.Poisonous = "No"
  or plants.Plant_Type = "Herb" and plants.Use = "Edible" and plants.Poisonous = "No"
  or plants.Plant_Type = "Vine" and plants.Use = "Edible" and plants.Poisonous = "No"

order by plants.Plant_Name



### I want to decorate the new yard for the house I bought. I'd like to choose some nice grass, and a couple trees, maybe some flowers.
### But I dont want my dogs or my kids to get a hold of something poisonous.

SELECT  
  plants.Plant_Name as name,
  plants.Plant_Type as type,
  plants.Preferred_Zone as zone,
  plants.Use as use,
  plants.Poisonous as poison,
  native.Time_to_Flower_Days as bloom

FROM 
  `kpolitte.The_Green_Gardener.plants` as plants
    left join `kpolitte.The_Green_Gardener.native` as native on plants.Plant_Name = native.Plant_Name

where 
  plants.Plant_Type = "Grass" and plants.Poisonous = "No"
  or plants.Plant_Type = "Tree" and plants.Poisonous = "No"
  or plants.Plant_Type = "Flower" and plants.Poisonous = "No"
  or plants.Plant_Type = "Vine" and plants.Poisonous = "No"

order by plants.Plant_Name

### My wife wants to grow her own plants, but she forgets to water them too much. I wonder if she could keep a cactus alive? 

SELECT  
  plants.Plant_Name as name,
  plants.Plant_Type as type,
  plants.Preferred_Zone as zone,
  plants.Use as use,
  plants.Poisonous as poison,
  native.Time_to_Flower_Days as bloom

FROM 
  `kpolitte.The_Green_Gardener.plants` as plants
    left join `kpolitte.The_Green_Gardener.native` as native on plants.Plant_Name = native.Plant_Name

where 
  plants.Plant_Type = "Cactus"
  or plants.Plant_Type = "Carnivorous"
  or plants.Plant_Type = "Succulent"

order by plants.Plant_Name


## I want to build my own home, and decorate it with edible plants that can also serve the purpose of being aesthetic, I hope you can also find some use for the tool I have built.
