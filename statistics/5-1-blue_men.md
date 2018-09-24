[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> Using scipy.stats.norm.cdf, I was able to determine the percentage of the US male population with heights between 5'10" and 6'1". I evaluated the standard normal CDF of the low range and subtracted that from the standard normal CDF of the high range. 

>> **34.2%** of US males lie in that range

```
import scipy.stats

meanMaleHeight=178
standardDeviationMaleHeight=7.7
rangeLow=177.8      # 5'10"
rangeHigh=185.4     # 6'1"

print "Percentage between 177.8cm-185.42cm: {}".format(scipy.stats.norm.cdf(rangeHigh,loc=meanMaleHeight,scale=standardDeviationMaleHeight)-scipy.stats.norm.cdf(rangeLow,loc=meanMaleHeight,scale=standardDeviationMaleHeight))
```
