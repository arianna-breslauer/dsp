[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> I used the thinkStats2 function to plot a probability mass function for respondents for the number of children under 18 in the respondents' households.
>> I used the thinkStats function to see what the pmf would look if the data was biased due to the class size paradox.
>> The class size paradox "describes the seemingly contradictory finding that the average person is associated with events, activities or organizations with more members than the average event, activity, or organization". (http://www.umasocialmedia.com/socialnetworks/glossary/class-size-paradox/)
>> I then plotted the two Pmfs together.
>> I then calculated the mean of each group. The mean of the biased group was 29.12 to 2d.p. which is much higher than the mean number of children under 18 given by the respondents of 1.02 to 2d.p..
```
import nsfg
import thinkstats2
import thinkplot

resp = nsfg.ReadFemResp()
pmf = thinkstats2.Pmf(resp.numkdhh, label = "numkdhh")

thinkplot.Pmf(pmf)
thinkplot.Config(xlabel='Number of children under 18', ylabel='PMF')

def BiasPmf(pmf,label):
	new_pmf=pmf.Copy(label=label)
	
	for x,p in pmf.Items():
		new_pmf.Mult(x,x)
	
	new_pmf.Normalize()
	return new_pmf

biased_pmf = BiasPmf(pmf, label = "biased")

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf,biased_pmf])
thinkplot.Show(xlabel='Number of children under 18', ylabel = 'PMF')

print ('Actual distribution mean',pmf.Mean())
print ('Biased distribution mean',biased_pmf.Mean())
```
