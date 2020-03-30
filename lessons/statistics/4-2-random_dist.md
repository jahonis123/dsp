[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)


## Import random module
import random  

## Create random numbers, use pmf 
random_numbers = np.random.random(1000)  
random_pmf = thinkstats2.Pmf(random_numbers)  

## Plot Distribution of PMF
thinkplot.PrePlot(1)  
thinkplot.Hist(random_pmf, align='right')  
thinkplot.Config(xlabel='Number', ylabel='PMF')  
### The distribution of PMF is not shown on the graph, as all of the numbers have the same PMF value to their key. 

## Calculate CDF and plot distribution 
random_cdf = thinkstats2.Cdf(random_numbers)  
thinkplot.Cdf(random_cdf)  
thinkplot.Cdf(thinkstats2.Cdf(random_cdf, label='random_cdf'))  
thinkplot.Config(xlabel='Number', ylabel='CDF')  
