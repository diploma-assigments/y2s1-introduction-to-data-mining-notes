
# Chapter 2 - Data Preprocessing
## Part 1

### Why preprocess data?
> **Accuracy:** correct data? (ex. -29 years old)
> **Completeness:** empty data
> **Consistency:** units used (ex. miles & km)

### Major tasks in Data Preprocessing
> **Data cleaning**
> - fill in missing values
> - smooth noisy data
> - remove outliers
> - fix inconsistency
> 
> **Data integration**
> - integrate multiple databases
> - data cubes
> - files
> 
> **Data reduction**
> - reduce dimension
> - compress data
> 
> **Data transformation**
> - normalization 

### Why Data cleaning?
> Due to human / computer error, faulty sensors etc
> 1. Incomplete
> 2. Noisy: outlier, error 
> 3. Inconsistent: (string type, integer type, different units)

### How to handle missing data?
> 1. delete the row / record that contain missing values
> 2. fill in manually by guess / look up
> 3. Fill in automatically with "unknown" or mean or prediction 

### How to handle noisy data?
> 1. **Binning:** sort & partition into equal-frequency bins, then smooth by bin mean/median/boundary
> 
> 2. **Regression:** fit data into regression functions
> 
> 3. **Clustering:** dect and remove outliers
> 
> 4. **Computer and human inspection:** computer detect sus values, human verify

### Aspects of data integration
##### 1. Schema integration:
> table A has `cust-id`, table B has `cust-#`, different name, need to treat as same

##### 2. Entity identification problem
> * One dataset says "Bill Clinton"
> * Another says "William Clinton"
> * They are the same person, but not obvious unless you match them smartly

##### 3. Data value conflict
> * Height from source A: `6 feet`
> * Height frmo source B: `183cm`
> * Both are correct, just different units
> 
> Can happen with different spellings, data format etc.

### Handling redundancy in data integration
> Same data from many sources, how?
> Detect using correlation analysis and covariance analysis

### Correlation analysis?
> 1. **chi-square test:** aka math
> 2. **visually evaluating correlation:** generate scatter plot, human see

---

## Part 2
### what is data reduction?
> reduce volume of data set, produce same analytical results

### Data reduction strategies
##### 1. Dimensionality reduction
> wavelet transforms
> Principal Components Analysis (PCA)
> feature subset selection

##### 2. Numerosity reduction
> regression
> histogram, clustering

##### 3. Data compression

### Why dimensionality in data is bad?
> 1. density and distance increase: clustering, outlier analysis become less meaningful
> 2. difficult to visualize / present

### What is data transformation?
> function that maps entire set of values to new one (select attributes / feature)

### Data transformation strategies
>  1. Smoothing: remove noise
>  2. Aggregation: Summarize attributes
>  3. Normalization: min-max, z-score, decimal scaling


![[images/img_c2_a.png|600]]

![[images/img_c2_b.png|600]]

![[images/img_c2_c.png|600]]


