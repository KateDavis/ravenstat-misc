1
in the attached by Stallard
Tables 3-6 -- just need the upper block Date of first exposure and Date of claim
In data frames

2
Build a set of data frames in which the dates of claims are by single year, not 5-year groups
Basically, let y = the cumulative number of claims, going across
Then build a splinefun of the cumulative number of claims
Interpolate the spline fun to individual years
Go from cumulative back to indiv year counts by subtraction
(Standard demographic stuff)

3
Then build a function
Given a vector of years of first exposure, injury (4-level injuries here), and current date
Return a data frame
     Variables year of future claim
     Expected number of claims (NOT rounded at this point)
Processing
   Each incoming vector element produces a set of probabilities, going across, based on single year of claim counts from 2 above
   Then add these probabilities across all vector elements
SInce the starting date will be in the middle of a year, you will have to prorate the first year of expected counts accordingly
You might allow for an additional weight vector on input

4
Build an inverter function
Suppose we have a matrix of counts from a trust that is in the same form as the Stallard matrix, but by year of claim
We also have a "from date" and a "to date" for dates of claims
We want to estimate how our trust's mix of claims by "Date of first exposure" compares with the Stallard mix
Simple inverter -- between "from date" and "to date" in each first exposure group, calculate the ratio of our total number of claims divided by the stallard number
Return a frame
        date of first exposure (grouped)
        ratio of us to stallard

5
You can feed these ratios into function 3 as "pseudo counts" to get the runoff curves for out trust's particular mix of first exposures
