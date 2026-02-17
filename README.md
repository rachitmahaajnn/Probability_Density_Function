# Probability_Density_Function
### Learning Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

## Objective

The objective of this assignment is to:
Transform the NO₂ feature using a roll-number-based nonlinear transformation.
Learn the parameters of a Gaussian-type probability density function.Estimate the parameters λ,μ and c from the transformed data.

## Dataset

Dataset: India Air Quality Data (Kaggle)
Feature Used: NO₂
Missing values were removed before processing.
File encoding issue was handled using latin1.


## Step 1: Data Transformation
Each value of NO₂ (x) was transformed using the function:
``` bash
z = x+ asin(bx)
```
Where:
``` bash
a=0.05(rmod7)
b=0.3((rmod5)+1)
```
Here:
r = University Roll Number
mod = Remainder operation
This transformation introduces non-linearity based on the roll number.

## Step 2: Parameter Estimation
We estimated parameters of the probability density function:
``` bash
p^​(z)=ce^(−λ(z−μ))
```

This form corresponds to a Gaussian distribution.
Parameter Computation:
``` bash
μ = Mean of transformed data z
σ = Standard deviation of z
λ=1/2σ^2
c=1/(2*pi*σ^2)^1/2​
```
The parameters were estimated using NumPy statistical functions.
## Implementation Details
Language: Python
Libraries Used:
pandas
numpy
matplotlib
scipy

## Key Steps:

Load dataset using proper encoding (latin1)
Clean column names
Extract NO₂ column
Remove missing values
Apply nonlinear transformation
Compute statistical parameters
Plot histogram with fitted PDF

### Model Verification
A histogram of transformed data was plotted and compared with the fitted Gaussian curve to verify model correctness.

## Final Output
The following values were obtained and submitted:
μ= 25.8063
λ= 0.00145
c= 0.02155

## Conclusion
The assignment successfully demonstrated:
Nonlinear feature transformation.
Parameter estimation of a Gaussian probability density function.
Statistical modeling using real-world air quality data.
