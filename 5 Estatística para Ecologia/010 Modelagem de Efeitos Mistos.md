

Mixed intercept effects? [Isabella R. Ghement on Twitter: "Mixed effects model tweeps, this terminology issue is bugging me: referring to random intercepts as "random intercept effects". Are they really "effects"? I thought effects require a predictor variable to be involved. " / X](https://twitter.com/IsabellaGhement/status/1603884459576942593)



  [https://dynamicecology.wordpress.com/2015/11/04/is-it-a-fixed-or-random-effect/](https://dynamicecology.wordpress.com/2015/11/04/is-it-a-fixed-or-random-effect/) 

 You wouldn’t take two measures and then try to estimate variance, but that is what you’re asking R to do if you treat it as random. Beyond that there is a lot of debate. But [many people think](http://stats.stackexchange.com/questions/37647/minimum-number-of-levels-for-a-random-effects-factor) you should have at least 5 levels (e.g. 5 sites) before you treat something as random. Some think even more. This is one place I see students really get in trouble a lot. They’ll have a blocking factor with 2 or 3 levels (year is a frequent culprit) and try to treat it as random. R will go ahead and report something, but it is pretty much the garbage estimate you would expect if you tried to estimate variance from 3 observations.