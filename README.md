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

### Identifying Predictors of MPG

<img width="811" alt="linear_regression" src="https://user-images.githubusercontent.com/108758105/202879337-a13d2e43-34d2-4f4b-80b7-8cd45867c220.png"> <br> 

<img width="905" alt="summary_mpgLRM" src="https://user-images.githubusercontent.com/108758105/202879402-e8347ce8-6bf4-4fc0-ba1d-b95bb5368ae2.png">

***Statistical Summary***

The data shows that the following variables provide a non-random amount of variance to the mpg values in the dataset: 

&emsp;&emsp;&emsp; • Vehicle Length <br>
&emsp;&emsp;&emsp; • Ground Clearance <br>

With p-values far less than the .05% threshold, the vehicle's length and ground clearance directly impact it's mpg performance.  While the vehicle's weight does get close enough for possible consideration, it does not meet the criteria for "non-randomness" of variance, statistically speaking.

With an overall p-value significantly below .05% threshold at 5.35e-11, we can reject the Null Hypothesis, therefore our model does not have a zero slope.

With an R-squared value of .7149, this model is fairly effective at predicting mpg of MechaCar prototypes at 71.5%. <br> <br>


### Summary Statistics on Suspension Coil

<img width="389" alt="total_summary" src="https://user-images.githubusercontent.com/108758105/202886078-410c0212-f556-4cd1-9440-b40a7464901c.png">

The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Collectively, it is apparent that the variance of 62.29356 is within the specified tolerance (image above). <br>

Upon further inspection, however, it becomes clear that not all lots are performing equally.  Lot 1 and Lot 2 are performing extremely well with a variance of less than 1 and a variance of 7.5, respectively.  Lot 3, though, far exceeds design specifications with a PSI variance of 170.3 (image below). <br>

<img width="544" alt="lot_summary" src="https://user-images.githubusercontent.com/108758105/202886328-42b93916-ca7b-497d-9dc3-dcde6fd0d1cb.png">

> *The box plot visualization below can provide further clarification as to the disparity in Lot 3 and how it impacts collective lots performance*

![lot_summary_boxplot](https://user-images.githubusercontent.com/108758105/202886525-929d68a3-f743-43c5-901b-956e7e60a822.png)

## T-Tests on Suspension Coils

> Collective Lot T-Test

<img width="911" alt="collectivePSI_tTest" src="https://user-images.githubusercontent.com/108758105/206062850-cc122358-a652-459d-be04-6566a855e13f.png">

After running a t-test on the suspension coil data using a presumed population mean of 1500, the actual mean is 1498.78 and with a p-value of .06028 (higher than the minimim threshold of 0.05) there isn't enough evidence to reject the null hypothesis because here isn't much of a statistical difference between the actual mean and the presumed poulation mean.

### Individual Lot T-Test

> Lot 1 T-Test\
> ***p-value = 1***
<img width="914" alt="lot1_tTest" src="https://user-images.githubusercontent.com/108758105/206065112-f0e5c1e7-7366-45e4-bef9-adbd8a74e218.png">


> Lot 2 T-Test\
> ***p-value = 0.6072***
<img width="904" alt="lot2_tTest" src="https://user-images.githubusercontent.com/108758105/206065162-da0001f4-043b-44a7-b1dc-287db0043a63.png">

The t-tests on the first two lots produced p-values exceedingly higher than the requisite threshold for rejecting the null hypothesis.  With having a mean near exact to the presumed population mean, it is clear that these two lots are statistically similar and therefore we cannot reject the null hypothesis.

> Lot 3 T-Test\
> ***p-value = 0.04168***
<img width="910" alt="lot3_tTest" src="https://user-images.githubusercontent.com/108758105/206065213-47a2b2b9-1d36-446d-a1ee-2cdff4841163.png">

Lot 3 on the other hand is well within range of statistical significance with a p-value of 0.04168, giving us enough room to reject the null hypothesis and deduce that there is a statistical difference between lot 3 and the presumed population mean.

## Study Design: MechaChar vs Competition.

Performance car sales is a game of brand and numbers, no one is bragging about a McClaren's safety rating. Highest horsepower, torque, price, etc.  Some companies find a sweetspot by offering the best value, however, and that would be the best strategy for AutosRUS.  Given the production issues, it may be best to accept offering the car at an optimal price that would overpower anything in it's price bracket and try to avoid going toe-to-toe with any brand founded on reliability.

In order to perform this study we will need to focus on a few variables such as:

&emsp;&emsp;&emsp; • Horsepower <br>
&emsp;&emsp;&emsp; • Price <br>
&emsp;&emsp;&emsp; • Drivetrain (AWD/FWD/RWD) <br>
&emsp;&emsp;&emsp; • Engine Type (4cyl/6cyl/Hybrid/Electric, etc) <br>
&emsp;&emsp;&emsp; • Doors (2dr/4dr/5dr) <br>

These metrics will suffice to perform a comprehensive study.  With the Price being the dependent variable, we can create our Null and Alternate Hypothesis.

> **NULL** Hypothesis - Based on the other metrics, and in comparison with the competition, the MechaCar is similarly (i.e. NOT competitively) priced and must be adjusted to compete. <br><br>
> **ALTERNATE** Hypothesis - Based on the other metrics, and in comparison with the competition, the MechaCar is competitively priced (statistically different with respect to the performance metrics).

Using the p-value of 0.05 as the standard and price as the dependant variable, we will test the MechaCar changing it's price to match competitor performance cars for comparisons.  We will utilize t-tests to guage statistical differences until we find a range where the MechaCar shows to have the highest value (most desireable/highest performance numbers within a specific price range).  The goal is to find a price range where we can reject the NULL hypothesis and accept the Alternate.
