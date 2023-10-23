

Mixed intercept effects? [Isabella R. Ghement on Twitter: "Mixed effects model tweeps, this terminology issue is bugging me: referring to random intercepts as "random intercept effects". Are they really "effects"? I thought effects require a predictor variable to be involved. " / X](https://twitter.com/IsabellaGhement/status/1603884459576942593)



  [https://dynamicecology.wordpress.com/2015/11/04/is-it-a-fixed-or-random-effect/](https://dynamicecology.wordpress.com/2015/11/04/is-it-a-fixed-or-random-effect/) 

 You wouldn’t take two measures and then try to estimate variance, but that is what you’re asking R to do if you treat it as random. Beyond that there is a lot of debate. But [many people think](http://stats.stackexchange.com/questions/37647/minimum-number-of-levels-for-a-random-effects-factor) you should have at least 5 levels (e.g. 5 sites) before you treat something as random. Some think even more. This is one place I see students really get in trouble a lot. They’ll have a blocking factor with 2 or 3 levels (year is a frequent culprit) and try to treat it as random. R will go ahead and report something, but it is pretty much the garbage estimate you would expect if you tried to estimate variance from 3 observations.
[Generalized linear mixed models: a practical guide for ecology and evolution: Trends in Ecology & Evolution (cell.com)](https://www.cell.com/trends/ecology-evolution/fulltext/S0169-5347(09)00019-6?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0169534709000196%3Fshowall%3Dtrue)


[A general and simple method for obtaining R2 from generalized linear mixed‐effects models - Nakagawa - 2013 - Methods in Ecology and Evolution - Wiley Online Library (mcgill.ca)](https://besjournals-onlinelibrary-wiley-com.proxy3.library.mcgill.ca/doi/10.1111/j.2041-210x.2012.00261.x)

