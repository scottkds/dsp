[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> ```python
>> import thinkstats2
>> import thinkplot
>> import nsfg
>> import numpy as np
>> 
>> def CohenEffectSize(group1, group2):
>>     """Computes Cohen's effect size for two groups.
>> 
>>     group1: Series or DataFrame
>>     group2: Series or DataFrame
>> 
>>     returns: float if the arguments are Series;
>>              Series if the arguments are DataFrames
>>     """
>>     diff = group1.mean() - group2.mean()
>> 
>>     var1 = group1.var()
>>     var2 = group2.var()
>>     n1, n2 = len(group1), len(group2)
>> 
>>     pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
>>     d = diff / np.sqrt(pooled_var)
>>     return d
>> 
>> # Read pregnancies
>> preg = nsfg.ReadFemPreg()
>> 
>> # Select lives births
>> live = preg[preg.outcome == 1]
>> 
>> # Seperate first births from second or later births
>> firsts = live[live.birthord == 1].totalwgt_lb
>> others = live[live.birthord != 1].totalwgt_lb
>> 
>> # Calculate and print the Cohen's d for brithweights
>> print('Effect size of first vs. later pregnancies:', CohenEffectSize(firsts, others))
>> 
>> ```
>>
>> 

