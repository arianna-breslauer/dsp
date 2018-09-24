[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> First I created the list of 1000 random values between 0 and 1. I then used the code from thinkStats to create the PMF and CDFs.  

![PMF](https://github.com/arianna-breslauer/dsp/blob/master/img/download.png)
![CDF](https://github.com/arianna-breslauer/dsp/blob/master/img/download-1.png)

>> Both the PMF and CDF show that the distribution is uniform. On the PMF, each random value has the same probability. On the CDF, the plot has a postive linear correlation as the cumulative distribution increases by the same amount for each incremental random value. 

```
import numpy as np
import thinkplot
import thinkstats2

randomNums = np.random.random(1000)

# PMF
pmf = thinkstats2.Pmf(t)
thinkplot.Pmf(pmf, linewidth=0.1)
thinkplot.Config(xlabel='Random number', ylabel='PMF')

# CDF
cdf = thinkstats2.Cdf(t)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='Random number', ylabel='CDF')
 ```
