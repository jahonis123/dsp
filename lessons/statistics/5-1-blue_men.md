[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

## How many people are between 5'10" and 6'1"?

## Use set mean, standard deviation, and scipy.stats.norm for standard deviation
mean = 178  
std_dev = 7.7  
dist = scipy.stats.norm(loc = mean,scale=std_dev)  

## Create function for unit conversion
def convert_in_to_cm(distance):  
    return distance / 0.393701  

## Set upper bound and lower bound of blue man group heights
lower_bound = convert_in_to_cm(5*12 + 10)  
upper_bound = convert_in_to_cm(6*12 + 1)  

## Use the cumulative distribution between the upper bound and the lower bound to find out the male population that can be in the Blue Man Group
percentage = dist.cdf(upper_bound) - dist.cdf(lower_bound)  
percentage  
0.3427485495516464  
34% of the male population can be in the Blue Man Group  
