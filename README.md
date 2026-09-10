# ECE-2112-PA-3

**Made by: Myk Zachary Marcian M. San Miguel | 2ECE-D 2026-'27**

This repository contains the contents of Programming Assignment 2 for our Advanced Computer Programming Course this S.Y. 2026-2027. This programming assignment covers three Python problems regarding Pandas.

Before we start, we need to load the pandas library so we can use it. After loading the pandas library, we would then load a `.csv` dataset supplied named `cars.csv`
```python
import pandas as pd
#this line of code loads the numpy library while giving it a cleaner name like "np"

cars = pd.read_csv('cars.csv')
#this lets us load the 'cars.csv' dataset into a variable named 'cars'
```
---

## Part A: Positional and Label-Based Slicing
### Objective
Complete the following after loading `cars`:
- Display the shape and complete list of column names of `cars`
- Create `cars_6_to_10` using positional slicing, where containing rows 6 to 10 of the dataset, where the first data is at row 1
### Discussion
- For the first cell, we need to display the shape of the dataset `cars`
```python
cars.shape
```
> this gets the shape of `cars` which is `(32, 12)`

- After that, this cell gets the rows 6 to 10 of the dataset and assigns it to `cars_6_to_10`
```python
cars_6_to_10 = cars.iloc[6:11]
```
> his selects rows 6 to 10. We typed `11` because if we would type `10`, it would only give us rows 6 to 9

- For `cars_6_to_10`, we would only display its Model, mpg, cyl, hp, and gear.
```python
cars_6_to_10_specs = cars_6_to_10.loc[:,['Model','mpg','cyl','hp','gear']]
```


## Part B: Model Lookup
### Objective
Use boolean indexing on the `Model` column to answer both requests:
- Display the complete row for `Toyota Corolla` and store it in a variable named `toyota`
- For `Pontiac Firebird`, display only `Model`, `mpg`, `hp`, and `wt`. Store this in a variable `pontiac`
### Discussion
- For the first cell, we would get the complete row for `Toyota Corolla`
```python
toyota = cars.loc[cars['Model']=='Toyota Corolla']
```
> this assigns it to variable `toyota`
- For the second cell, this would display the Model, mpg, hp, and wt of the `Pontiac Firebird`
```python
pontiac = cars.loc[cars['Model']=='Pontiac Firebird',['Model','mpg','hp','wt']]
```
> we would assign the result to the variable named `pontiac`

## Part C: Multi-Model Subsetting
### Objective
Create a DataFrame named `selected_cars` containing only the records for three models of cars: `Datsun 710`, `Lotus Europa`, `Ferrari Dino`.
### Discussion
- For this cell, we would select `Datsun 710`, `Lotus Europa`, `Ferrari Dino` using their Model names. Moreover, we would only get the `['Model','mpg','cyl','hp','gear']` of these selected cars
```python
selected_cars = cars.loc[
  (cars['Model'] == 'Datsun 710')|
  (cars['Model'] == 'Lotus Europa')|
  (cars['Model'] == 'Ferrari Dino')
  ,['Model', 'mpg', 'cyl', 'hp', 'gear']  ]
```
- For the next cell, we would display the dataset `selected_cars` in tabular form. After that we would output the shape of this data set
```python
display(selected_cars)
print('\nShape: ',selected_cars.shape)
```

---
## Final Remarks
Thank you so much for giving your time to read this README file.

## History 
**September 3, 2026** - This repository was created\

**September 10, 2026** - Inputs the main contents of the README and uploads the `.ipynb` file as well as the `.csv` file
