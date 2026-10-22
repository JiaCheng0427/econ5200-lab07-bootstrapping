# Diagnosing Broken Confidence Intervals

## Objective

In this lab, I tested different bootstrap methods to understand why confidence intervals can sometimes give misleading results.

## Methodology

- Used Python and NumPy to analyze bootstrap confidence intervals.
- Tested the median age of 32,561 people using 2,000 bootstrap samples.
- Compared parametric and bootstrap confidence intervals using 400 simulations of skewed data.
- Analyzed wage data from 1,000 workers across 25 firms.
- Compared ordinary bootstrap and cluster bootstrap methods.
- Used a `bootstrap_utils.py` module to calculate confidence intervals.
- Used AI to write a coverage function, revised my prompt, and checked its results.

## Key Findings

**1. Bootstrap with no variation**

The sample median age was 37, and the bootstrap standard error was 0.000000. The BCa method returned NaN with a warning. This showed me that a zero standard error does not mean the true median is known exactly.

**2. Confidence intervals with skewed data**

I found the following coverage rates:

- Mean, parametric: 92.5%
- Mean, bootstrap: 92.0%
- Median, parametric: 66.8%
- Median, bootstrap: 92.8%

The parametric method performed poorly for the median. I learned that using the wrong interval for a parameter can lead to misleading results.

**3. Cluster bootstrap**

The ordinary bootstrap interval was 5.7 times narrower than the cluster bootstrap interval. Its coverage was only 19.5%, compared with 91.0% for the cluster bootstrap.

This showed me why it is important to consider relationships between workers in the same firm.

**4. AI-assisted coding**

I used AI to write a coverage function and revised my prompt to make the random seed instructions clearer. After testing the function, the AI results matched my earlier results exactly: 19.5% for the ordinary bootstrap and 91.0% for the cluster bootstrap.

## Conclusion

This lab helped me understand that code can run correctly while giving misleading statistical results. I also learned that choosing the right bootstrap method depends on the structure of the data.
