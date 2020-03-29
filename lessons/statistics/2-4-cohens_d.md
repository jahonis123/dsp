[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

# Separate the firstborns and others 
frstborn = live.loc[lambda live: live['birthord'] == 1]  
otherborn = live.loc[lambda live: live['birthord'] != 1]

# Create the variables for Cohen's d - 
x1mean = frstborn.totalwgt_lb.mean()  
x2mean = otherborn.totalwgt_lb.mean()

# Create variable s
var1 = frstborn.totalwgt_lb.var()  
var2 = otherborn.totalwgt_lb.var()  
count1 = frstborn.count()[0]  
count2 = otherborn.count()[0]  
s = (var1*count1 + var2*count2)/(count1+count2)  

# Put all variables together to form d
d = (x1mean-x2mean)/(s)  
d = -0.06302351187909945  
