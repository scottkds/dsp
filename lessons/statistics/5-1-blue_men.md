[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> ```python
>> """By using scipy.stats.norm.cdf I was able to determine the percentage of men
>> with height less than or equal to a height specified in feet and inches. Taking
>> the percentage of men that have a heiht of 6.1 and subtracting the the percentage
>> of men that have a height of 5 foot 10 inches or less we can know approximately
>> how many men in the population would meet the Blueman Group's height requirments."""
>> 
>> from scipy.stats import norm as n
>> 
>> def inches_to_cm(inches):
>>     """Converts inches to centimeteres"""
>>     return inches * 2.54
>> 
>> def feet_to_cm(feet):
>>     """Converts feet to centimeters"""
>>     return feet * 12 * 2.54
>> 
>> def height_in_cm(feet, inches):
>>     """Converts the parameters feet and inches to a single centimenter output"""
>>     return (feet_to_cm(feet) + inches_to_cm(inches))
>> 
>> def percent_of_men_less_than_height(feet, inches):
>>     """Returns the percentage of men that have a height less than or equal to
>>     feet and inches"""
>>     return n.cdf(height_in_cm(feet, inches), loc=178, scale=7.7) * 100
>> 
>> percent_of_men_less_than_height(6, 1) - percent_of_men_less_than_height(5,10)
>> ```
>>
>> 

