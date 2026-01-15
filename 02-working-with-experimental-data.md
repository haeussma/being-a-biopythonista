# Photometric reaction data

In this chapter, we will build on the basics from the previous chapter. First we will read in kinetic data measured conducted with a plate reader in a micro titer plate. We will plot the data, subtract the background, create a calibration curve, and calculate the initial rate of the reaction.

## 1. Read in the data

Within a new notebook, import `pandas` and read in the kinetic data, which is stored as a CSV file in [data/](`data/`) folder.

> 1. Check how to read in a CSV file using `pandas`
> 2. Use `matplotlib` to plot the calibration and kinetic data separately

## 2. Clean the data

> 3. Subtract the "blank" column from the kinetic and calibration data

## 3. Create a calibration curve

> 4. Extract the calibration data, and use `scipy` to perform a linear regression. Investigate what kind of metrics the linear regression function returns

> 5. Define a funtion called `to_concentration` that converts the measured absorbance to concentration using the calibration results

## 4. Calculate the initial rate of the reaction

> 6. Extract the kinetic data, and use the `to_concentration` function to convert the absorbance to concentration. Store the calculated contenttrations in new columns in the original pandas dataframe.

> 7. Plot the kinetic data as a function of time, and the concentration as a function of time

> 8. Calculate the initial rate of the reaction for each well. 