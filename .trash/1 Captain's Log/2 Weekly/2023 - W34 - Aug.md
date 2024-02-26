## WEEKLY SUMMARY
Brian took a look at the model fit with the terraclim data and said he has no clue why it works so shittily.

Now it's my turn to finish adding in all the data and run the model in all possible shapes and forms so we can start finally looking for results.

# August 23rd - Wednesday

- Finish running the split model with the form they gave, divided by precipitation ranges, as well as cwd and radiation and the others.
- Look at the coefficients for the equations in all three ranges - low, medium and high - and the R squared. List out their magnitudes so we understand better how they behave.
- work through the math to figure out the functional form
- Add yearly data

		monthly <- pars['env']*(pars['jan']*data$jan + pars['fev']*data$fev + ... + pars['dec']*data$dec)
		yearly <- same but even longer?...

I have been working on other things that feel easier - reading articles, studying stats, improving on my Obsidian library... Basically everything that I want to do on the weekend but shouldn't be doing right now. I believe it is because the task of coding feels enormous and hard to begin. I need to break it down into even smaller chunks.

- Run the model with small chunks by precipitation, first and foremost. See if you identify a change in parameters with each section.
- Run the medians/means with the functional form and see how that looks like
- Try the same with cwd.

Let's really focus on the research and leave Obsidian for later, when you want to rest instead.

First you investigate what you have right now. Next week you'll add:
- mature forest cover
- historical data
- radiation
- MODIS burned area vs. MAPBIOMAS
- GEDI biomass vs. ESA
- Number of deforestation events as a predictor of disturbance (as done on heinrich 2021)


1) Running the model with medians within the ongoing functional form:
First I try to just predict biomass from age.

The growth curve, when fit on summarized data, does not perform much better than a linear model. Considering the mean squared error:
> mean((data$agbd - predicted_values)^2)
[1] 128.3397
> mean((data$agbd - pred)^2)
[1] 112.9807

there's a small improvement.

Considering precipitation ranges:

|  | Prec value | Intercept | Slope | R squared |
|----------|----------|----------|----------|----------|
| means | low| 105.9699 | 1.1794 | 0.4447 |
| means | mid | 80.2443 | 0.9424 | 0.5797 |
| means | high | 55.0872 | 1.7959 | 0.8197 |
| medians| low | 105.7249 | 1.2045 | 0.393 |
| medians| mid |  76.7156 | 1.1386 | 0.5951 |
| medians| high | 47.3294 | 1.8342 | 0.7957 |


![[Screenshot 2023-08-23 161933.png]]

With CWD instead:

|  | Prec value | Intercept | Slope | R squared |
|----------|----------|----------|----------|----------|
| means | low| 90.6488 | 1.5063 | 0.8387 |
| means | mid | 94.2284 | 1.3524 | 0.7191 |
| means | high | 88.3080 | 1.8287 | 0.7687 |
| medians| low | 82.8864 | 1.7821 |  0.8366  |
| medians| mid |  85.3769 | 1.7416 |  0.7573 |
| medians| high | 79.6420 | 2.0424 | 0.7844 |

Weird - the CWD values are positive in Terraclimate, which makes sense to me, because it's a positive measure of stress - but in Heinrich's paper, the values are negative?

Investigating the source of Heinrich's paper, I noticed that:
A complementary measure of drought severity is the maximum cumulative water deficit (_MWD_), which corresponds to the maximum value of the accumulated water deficit (_WD_) reached for each pixel within the year. For this, we first calculated the monthly _WDs_ based on the approximation that a moist tropical canopy transpires ∼100 mm month−1. This value is derived from the mean evapotranspiration obtained by ground measurements in different locations and seasons in Amazonia

Poorter states that:


Using Poorter's data:

|  | Prec value | Intercept | Slope | R squared |
|----------|----------|----------|----------|----------|
| means | high| 79.8254 | 1.2372 | 0.6723 |
| means | mid | 85.1371 | 1.7383 | 0.7864 |
| means | low | 82.1837 | 1.9066 | 0.8581 |
| medians| high | 73.2008 | 1.4926 |  0.7869  |
| medians| mid |  76.8182 | 2.0535 |  0.7879 |
| medians| low | 72.1799 | 2.3513 | 0.8765 |

![[Screenshot 2023-08-23 173620.png]]

#################################

Out of curiosity, I tried to fit the data with only age and this mean annual cwd.

By fitting right away, once more, the predicted values converged to a local minima near the asymptote.

Grouping by low/med/high cwd, optim is way underperformed by lm:
With high cwd:
lm: mean((data$agbd - predicted_values)^2)
52.54239
optim: mean((data$agbd - pred)^2)
163.5283
Predicted vs observed:
![[Screenshot 2023-08-23 175424.png]]
With low cwd:
lm: mean((sum_stats$agbd - predicted_values)^2)
 68.09265
optim: mean((data$agbd - pred)^2)
 219.7581
Predicted vs observed with the growth curve:
![[Screenshot 2023-08-23 175724.png]]

Out of curiosity, I tried to run Heinrich's data on optim.
And lo and behold - getting stuck on local minima, and not generating any interesting new outputs!

So, it really does seem like the issue is with the fitting stage somehow. I would like to investigate closer with different fitting methods to try to understand what am I doing wrong with optim, as this code has definitely worked with nls with the same data.


I like the idea of weekdays to progress on research, and weekends to write/study/read - some light work when my brain is fried.
Also, this weekend I want to try to learn how to work with TPOT.



# August 22nd - Tuesday

Nonlinear regression model
  model: Corrected_AGB ~ 112 * (1 - exp(-theta2 * age))^theta3
   data: precip_1920
 theta2  theta3 
0.02766 1.11411 
 residual sum-of-squares: 1038

I am trying to run the model with different precipitation as well as cumulative water deficit values.
Out of curiosity, I tried:
```{R}
fit <- lm(data$agbd ~ data$age)
Multiple R-squared:  0.05989,   Adjusted R-squared:  0.05989 

fit <- lm(data$agbd ~ data$prec)
Multiple R-squared:  0.03339,   Adjusted R-squared:  0.03339 

fit <- lm(data$agbd ~ data$prec + data$age)
Multiple R-squared:  0.1029,    Adjusted R-squared:  0.1029 
```

Also, the R squared of the median agbd per age was 0.6. Way better than 0.06!

Brian mentioned to try the means just out of curiosity and then start splitting by precipitation like they did in the paper.
That generated a slightly better R squared - 0.6233 vs 0.6052.

Out of curiosity I tried mean and median biomass by temperature value - and that was absolutely atrocious, 0.00024. Not a predictor at all.

So the summary outcome of today:

- Finish running the split model with the form they gave, divided by precipitation ranges, as well as cwd and radiation and the others.
- Look at the coefficients for the equations in all three ranges - low, medium and high - and the R squared. List out their magnitudes so we understand better how they behave.
- work through the math to figure out the functional form.

Think of fitting it with a NLS - although that is not the main focus right now, it could be an interesting, fast way of trying to investigate the issue.

I also had a meeting with Fiona not that long ago.
Fit precipitation and soil type as interacted terms - the effect of precipitation depends on sandiness and drought stress will depend on soil type.

Fitting by region may not be the best approach, as it was done on Heinrich et al - but I can run the model for different regions of the forest and investigate if the relationship I find is different.
Also, I should look into cations and the phosphorus gradient across the basin - maybe look for a continuous phosphorus data source.

# August 20th - Sunday

I think today I can think - if I were to show this to Brian tomorrow, what would I show?
And go from there. I think for this the priority isn't even the mature forest mask, it's running the models again and trying to understand what is wrong with them, and they will understand if I say it's work in progress as I've had literally two less days left to work this week - so many other hangouts... It happens.
So tomorrow early morning, I finish the run_model script - run the original dataframe as well as the new one and try to investigate the relationships better. Right now, it should be about understanding optim's behavior and output.

The coming week, I also would like to investigate TPOT and how it works.

# August 19th - Saturday

Today goals:
- finish mature forest info
- unite everything into one script
- run the model in every imaginable shape and form. make switches. keep everything visible.

Spent a good portion of today working on pretty much all other sorts of life organization and errands, except for my work. I am okay with having needed to get those things done, but I need to learn to put the mess aside and just get to work first thing. Now I will continue with the pomodoro technique until 10pm - there's no need to work many hours, just get the task done and we can move on with the week. So far so good. Things are definitely much better than they used to be. This can and will be done soon.

Planning pomodoro:
- 1 block to finish mature forest masking
- 1 block to run the model again with mature forest information and soil information

Obsidian is progressing slowly but surely.

I find the 10mg of vyvanse is too low for sure. Haven't been as focused as I should've been, and as I was with 20. I'm sure 30 will be even better.

I am thinking of writing a unique script now with all the switches so the model can be better understood.

```
** also realizing it's good to not split the desktop too much - it's preferrable to avoid too many distractions. remember that multitasking is impossible! it does naht eczist ** 
```

The temptation to start from the get go is great, but we must hold on to the task at hand.
I think it's just the fear that something bad happening way in the past would affect what we do right now, but we've already confirmed. Also, the main thing is the model - the data's distributions make sense and so should the model. Finish, understand the process of fitting, then go comb from the beginning. Patience.

On Friday, I went down to campus to work with Morgane, but TH was incredibly loud and impossible to focus in. I came home late and could not work so I focused on getting obsidian set up, as I needed to have an organization system set so I could work.

Right now all I want is a full day by myself with a high vyvanse dose so I can finish everything - get done with all regions of the amazon, look over the entire code. This week, this day shall happen!
Ideally, it'd be Tuesday. But I have my meeting then, so well, so be it. I'll have the meeting and show them what I have and then focus like crazy for the coming week, no distractions.

It's 9:20 and the mature forest mask indexing issue is solved. Just gotta polish the pseudocode tomorrow.

Tomorrow early morning, before Hossein's BBQ, I can work more on this. Tonight I feel stressed as most of the day flew by and I did not finish everything that I wanted. Still, I know the source of this stress is the meeting that has been anticipated for Tuesday - and in the end, those meetings are not the end of the world. I will take my medication at a higher dose this week and I have better systems set in place. Now I will choose a good morning alarm and go to sleep, probably will take medication to crash and fix my cycle. One day at a time.

-----------------

When looking at AET and CWD for these regions, we see not a ton of interannual variation, but some very strong seasonality.

PET is derived from vapor pressure, radiation, soil heat, temperature, wind speed. Land surface temperature came from MODIS. The rest is from meteorological station data.

Actual evapotranspiration is counted as the liquid
water supply plus the soil water utilized - 

CWD being zero could be just truncation as AET is high.
Units are milimiters per month.

I initially run the model with the total sum of all monthly and yearly cwd. CWD is dependent on AET so it doesn't make sense to fit them both in the model at once, so I tried them separately.

What are the changes in water stress. Standard deviation could be fit.
Variance rather than the mean.
Look at whether people have controlled for variance. Go back to make sure that people are 
Temporal amalgamation
Yearly, fit with separate coefficients
Monthly
Try a few different interaction terms and see what happens.
Evapotranspiration and growth

Okay - now it's time to do a million fits.
likelihood - NLL[o$par] [[Likelihood vs. Probability]]



Is precipitation seasonality defined in poorter 2021
Prec seasonality.
What was done with the grasslands for calibration?

Modelling every year.


So we fit into the model both total AET and CWD, yearly, and monthly values.

AET varies from 0 to 1000, CWD from 0 to around 400. No negative values


What to ask Fiona

- Evapotranspiration and CWD - 

fit precipitation and soil type as interacted terms.

drought stress


soil type depends on what soil was underneath

continuous soil phosphorus information. look into it. 

soil texture, cations...

Fitting by region.

August 18th - Friday

I am finishing the mature forest asymptote
Finishing the soil map
Finishing all weather information
Going back and double checking the whole code to send that to Brian and guarantee it's in good shape.

And then find out what's wrong with the fitting.
Justify everything with the poorter and heinrich papers
...and hope for the best.

# August 16th

Model was run with aet and cwd from terraclimate.

yearly total aet:
![[aet 2001-2017.png]]

![[aet monthly.png]]
monthly total aet:
![[aet 85-2000.png]]


monthly total cwd:
![[cwd monthly.png]]
yearly total cwd:
![[Screenshot 2023-08-16 111806.png]]

![[Screenshot 2023-08-16 111820.png]]
total cwd across 33 years:
![[total CWD.png]]

Biomass histogram
![[Screenshot 2023-08-16 103129.png]]
total aet histogram
![[total_aet_hist.png]]
total cwd histogram
![[total_cwd_hist.png]]

weirdly, they were both converging to the asymptote.
Brian looked at likelihood values and tested with minimal expected values - say, we expect mathematically that it will converge to the mean - and compared the results. It was weird that it would converge to a value very close to the given asymptote.

It seems like the function has many local minima around the asymptote.