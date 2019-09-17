[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> ```python
>> """Comments: When the observer of a group is outside the group then things will
>> appear differently than when the observer of the group is within the group. In
>> the class size example the dean lists 4 classes of 20 to 24 sutdents (median class
>> size 22) and so you would have 4 classes of roughly size 22 encompassing 88 students
>> total where as if you asked the each of the students you would have to multiply
>> the probability of a class size of 22 by the number of students in that class which
>> would cause a large bias in the apparent probability."""
>> 
>> # Imports
>> import thinkstats2
>> import thinkplot
>> import nsfg
>> 
>> # Read in Female Responses
>> resp = nsfg.ReadFemResp()
>> 
>> # Create two PMFs, one for actual and one to be biased
>> actual = thinkstats2.Pmf(resp.numkdhh, label='actual')
>> kids = actual.Copy(label='kids_biased')
>> 
>> # Bias the kids PMS
>> for key, value in kids.Items():
>>     kids.Mult(key, key)
>> kids.Normalize();
>> kids.Total();
>> 
>> # Display the plots simultaniously
>> thinkplot.preplot(2);
>> thinkplot.Pmfs([actual, kids]);
>> thinkplot.Show(xlabel='class size', ylabel='PMF');
>> ```
>>
>> 

