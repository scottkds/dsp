[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

>> ```python
>> """Using the formula for Pearson's  median skewness I wrote the function p_skew(values)
>> that calculates the Pearson's median skewness for a sample of data. The result is
>> that p_skew returns -0.338 which indicates the data is left skewed. Displaying a
>> Probability Density Function shows and it is apparent that the data is left skewed."""
>> 
>> # Imports
>> import hinc2
>> import hinc
>> import numpy as np
>> import thinkstats2
>> import thinkplot
>> import math
>> 
>> # Define p_skew for Pearson's median skewness
>> def p_skew(values):
>>     """Calculates the pearson skewness of a sample of data"""
>>     return 3* (values.mean() - np.median(values)) / values.std()
>> 
>> # Read in the data using
>> df = hinc.ReadData()
>> ls = hinc2.InterpolateSample(df);
>> 
>> # Calculate the mean, media, and standard deviation for printing.
>> mean = round(ls.mean(), 3)
>> median = round(np.median(ls), 3)
>> std = round(ls.std(), 3)
>> 
>> # Print the mean, median, standard deviation, and Pearson's mendia skewness.
>> print('Mean:', mean, 'Median:', median, 'Std:', std)
>> print(round(p_skew(ls), 3))
>> 
>> # Create and display a PDF of the log sample of the incomes
>> pdf = thinkstats2.EstimatedPdf(ls)
>> thinkplot.Pdf(pdf, label='Log Sample of Incomes')
>> ```
>>
>> 

