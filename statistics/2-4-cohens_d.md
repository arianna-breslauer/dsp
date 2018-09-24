[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> To see whether first babies are lighter or heavier than others, I looked at the mean values for 'totalwgt_lb' for each respective group. To do this, I called the functions firsts.totalwgt_lb.mean() and others.totalwgt_lb.mean(). The mean for the 'others' group is slightly higher than that of the 'firsts' group.
>> To calculate the effect size of this difference, I used the CohenEffectSize computation, as provided by ThinkStats.
>> Cohen's d = -0.0887 to 3 s.f.. The negative sign indicates that first babies tend to be lighter than others.
>> Conversely, for pregnancy length, Cohen's d was positive but smaller. The positive sign of the statistic means that pregnancy lengths for first babies tend to be longer than for other pregnancies.

```
import nsfg
import first

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

# Mean pregnancy lengths for first babies and others
firsts.prglngth.mean(), others.prglngth.mean()

# Cohen's d
def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    
    group1: Series or DataFrame
    group2: Series or DataFrame
    
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d
 
print "Cohen's D for Pregnancy Length Between First Babies and Others: {}".format(CohenEffectSize(firsts.prglngth, others.prglngth)) 
print "Cohen's D for Total Weight Between First Babies and Others: {}".format(CohenEffectSize(firsts.totalwgt_lb,others.totalwgt_lb))
```
