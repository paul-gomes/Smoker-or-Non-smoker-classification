
# Initial Exploration

Dataset has 7 feature - 'age', 'sex', 'bmi', 'children', 'smoker', 'region', 'charges'. 
1. age         1338 non-null int64
2. sex         1338 non-null object
3. bmi         1338 non-null float64
4. children    1338 non-null int64
5. smoker      1338 non-null object
6. region      1338 non-null object
7. charges     1338 non-null float64

### Data Transformation

It looks like all of the featuers are important for forcasting the insurance costs. However, some of the important features - 'smoker', 'region' is in object. As a result, I had to convert them to numerical values before I can feed them into the model. </br>
I have converted 'smoker' feature into numerical by replacing 1 for "yes" and 0 of "no" and named the new feature 'isSmoker'. I have converted 'region' into numerical by replacing 1 for 'southwest', 2 for 'southeast', 3 for 'northwest', and 4 for 'northeast' and named the the new feature 'region_num'. That is all the regions the dataset has.

### Correlation 

|  | age | bmi | children | charges | isSmoker | region_num |
|------------|-----------|-----------|-----------|----------|-----------|------------|
| age | 1.000000 | 0.109272 | 0.042469 | 0.299008 | -0.025019 | -0.002127 |
| bmi | 0.109272 | 1.000000 | 0.012759 | 0.198341 | 0.003750 | -0.157566 |
| children | 0.042469 | 0.012759 | 1.000000 | 0.067998 | 0.007673 | -0.016569 |
| charges | 0.299008 | 0.198341 | 0.067998 | 1.000000 | 0.787251 | 0.006208 |
| isSmoker | -0.025019 | 0.003750 | 0.007673 | 0.787251 | 1.000000 | 0.002181 |
| region_num | -0.002127 | -0.157566 | -0.016569 | 0.006208 | 0.002181 | 1.000000 |

![Correlation](/images/correlation.PNG)

There are no missing values. So, I would not be needing any cleaning here. After analyzing the dataset, It looks like there is a strong correlation between 'isSmoke' and 'charges', which is .787, a strong positive correlation. There is also a correlation between 'age' and the 'charges', which is .299, a weak positive correlation. 

[Notebook link- Initial Exploration](/initial_exploration.ipynb)