# MechaCar Analysis

## Overview 
* Identify which variables in the dataset predict the mpg of MechaCar prototypes.
* Collect summary statistics on the PSI (lbs/in^2) of the suspension coils from the manufacturing lots.
* Determine if the manufacturing lots are statistically different from the mean population.
* Compare vehicle performance of the MechaCar vehicles against vehicles from other manufacturers. <br> <br>

#### ***Resources:*** <br>
>
> *Software:* &emsp; R 4.2.1, RStudio 2022.07.2+576 <br>
> *Datasource:* &emsp; MechaCar_mpg.csv, Suspension_Coil.csv <br>

### Identify Predictors of MPG

<img width="811" alt="linear_regression" src="https://user-images.githubusercontent.com/108758105/202879337-a13d2e43-34d2-4f4b-80b7-8cd45867c220.png"> <br> 

<img width="905" alt="summary_mpgLRM" src="https://user-images.githubusercontent.com/108758105/202879402-e8347ce8-6bf4-4fc0-ba1d-b95bb5368ae2.png">

***Statistical Summary***

The data shows that the following variables provide a non-random amount of variance to the mpg values in the dataset: 

&emsp;&emsp;&emsp; • Vehicle Length <br>
&emsp;&emsp;&emsp; • Ground Clearance <br>

With p-values far less than the .05% threshold, the vehicle's length and ground clearance directly impact it's mpg performance.  While the vehicle's weight does get close enough for possible consideration, it does not meet the criteria for "non-randomness" of variance, statistically speaking.

With an overall p-value significantly below .05% threshold at 5.35e-11, we can reject the Null Hypothesis, therefore our model does not have a zero slope.

