[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

## Download Data
resp = nsfg.ReadFemResp()

## Split out unbiased and biased datasets
unbiased = resp.numkdhh  
biased = resp.numkdhh.loc[resp['numkdhh'] > 0]

## Calculate mean of both unbiased and biased datasets
print(unbiased.mean())  
print(biased.mean())  
1.024205155043831  
1.9186274509803922  

## Create distributions of actual and biased datasets
actual = thinkstats2.Pmf(unbiased, label = 'actual')  
biased = thinkstats2.Pmf(biased, label = 'biased')  
actual  
Pmf({0: 0.466178202276593, 1: 0.21405207379301322, 2: 0.19625801386889966, 3: 0.08713855815779145, 4: 0.025644380478869556, 5: 0.01072877142483318}, 'actual')  
biased  
Pmf({1: 0.4009803921568629, 2: 0.36764705882352944, 3: 0.1632352941176471, 4: 0.04803921568627452, 5: 0.020098039215686276}, 'biased')

## Plot distributions
thinkplot.PrePlot(2)  
thinkplot.Pmfs([actual, biased])  
thinkplot.Config(xlabel='Children under 18', ylabel='PMF')  
