# DR25-occurrence
Python notebooks that explain the computation of various DR25 occurrence rate products

If you're not used to Bayesian modeling, start with lineFitting.ipynb, which introduces the concepts in the context of fitting a line to data.  Then work through binomialPointProcessConstantRate.ipynb and binomialPointProcessVariableRate.ipynb, which apply these techniques to a binomial point process in 2D as a warmup to DR25 vetting completeness and reliability analysis.  As checked in, binomialPointProcessVariableRate.ipynb detects a barely-resolved signal of reduced probability in the lower right corner.  You can try other models which have more obvious signals if you run the notebook.

The Bayesian approach using a binomial point process is applied to DR25 analysis in the relatively simple case of binomialVettingCompleteness.ipynb.  DR25 reliability is addressed in binomialReliability.ipynb.

There are also examples using a Poisson point process, but I concluded that this is not suitable for DR25 vetting and reliability analysis.

For a description of DR25 and the data behind this analysis, see https://arxiv.org/pdf/1710.06758.pdf.
