# investigating Heinrich data with optim vs. linear model

library(ggplot2)

#Set the working directory will need to change for each user

setwd("/home/aavila/forest_regrowth/heinrich_poorter/Fig1_data_input/Fig1_data_input/")

  

########### Load the point data ####################

  

# Creating a name of data and reading the csv table

dados2<-read.csv2("MCWD_assessment_may2020_CHIRPSv1.csv",sep=",")

dados2$Corrected_AGB = dados2$Corrected_AGB/2

  

dados2 <- dados2[,c(1,3,5)]

colnames(dados2) <- c('age', 'agbd', 'threshold')

mcwd_0<-dados2[dados2$threshold == 0,]

mcwd_180<-dados2[dados2$threshold == -180,]

mcwd_277<-dados2[dados2$threshold == -277,]

mcwd_350<-dados2[dados2$threshold == -350,]

  

data <- mcwd_0

  

fit <- lm(data$agbd ~ data$age)

summary(fit)

#             Estimate Std. Error t value Pr(>|t|)    

# (Intercept)   4.5383     3.5828   1.267    0.215    

# data$age      2.3964     0.1895  12.647 1.49e-13 ***

# ---

# Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

  

# Residual standard error: 9.897 on 30 degrees of freedom

# Multiple R-squared:  0.8421,    Adjusted R-squared:  0.8368

# F-statistic: 159.9 on 1 and 30 DF,  p-value: 1.487e-13

  

predicted_values <- predict(fit, as.data.frame(data$age))

  

ggplot(data, aes(x = age, y = agbd)) +

  geom_point() +

  geom_smooth(method = "lm", se = FALSE, color = "blue") +

  theme(text = element_text(size = 20))

  

# cool. now we try with optim:

  

G <- function(pars) {

    pars['B_0'] + pars['B_1'] * data$age

}

  

pars = c(B_0 = 1, B_1 = 1, sd = 0.05)

  

neg_r_squared <- function(pars) {

  Gpred <- G(pars)

  residuals <- Gpred - data$agbd

  neg_rsq <- -(1-sum(residuals^2) / sum((data$agbd - mean(data$agbd))^2))

  return(neg_rsq)

}

  

o = optim(par = pars, fn = neg_r_squared) #, method = "L-BFGS-B")

o

  

# cool - so with r squared optim gets the exact same value as the lm when using L-BFGS-B.

# it's slightly off with the default method but it gets a slightly higher R squared.

  

# now we try the same, but with NLL instead of neg r squared

  

NLL = function(pars) {

  if(pars['sd'] < 0){ #avoiding NAs by keeping the st dev positive

    return(-Inf)

  }

  # Negative log-likelihood

  print(-sum(dnorm(x = data$agbd - G(pars), mean = 0, sd = pars['sd'], log = TRUE), na.rm = TRUE))

}

  

o = optim(par = pars, fn = NLL, method = "L-BFGS-B")

o

  

# and NLL won't find the correct value with the default method - it needs L-BFGS-B to work.

  

# now let's try the growth curve as we have used it so far.

  

G <- function(pars) {

  pars['B_0'] + pars['A'] * (1 - exp(-pars['age']*data$age))

}

  

pars = c(B_0 = 10, A = 100, age = 100, sd = 0.05 )

o = optim(par = pars, fn = NLL, method = "L-BFGS-B")

o

  

residuals <- G(o$par) - data$agbd  

sum(residuals^2) / sum((data$agbd - mean(data$agbd))^2)

# the function is converging to the mean - G(o$par) is the mean.

  
  

# let's check the functional form.

  

# here's the result of her fit of the same model with nls:

  

# Nonlinear regression model

#   model: Corrected_AGB ~ 133 * (1 - exp(-theta2 * age))^theta3

#    data: mcwd_0

#  theta2  theta3

# 0.02992 1.11620

#  residual sum-of-squares: 2695

  

# Number of iterations to convergence: 5

# Achieved convergence tolerance: 1.19e-06

  

plot(data$age, data$agbd)

curve(  133 * (1 - exp(-0.02992*x))^1.1162, add = TRUE)

residuals <- data$agbd - 133 * (1 - exp(-0.02992*data$age))^1.1162

(1-sum(residuals^2) / sum((data$agbd - mean(data$agbd))^2))

# that's a higher R squared (0.8551369) with the curve and the known parameters from nls

# which makes sense.

# interesting thing here is that the exponent 1.1162 makes a difference

to be considered in upcoming iterations.

  

# just for the hell of it, let's try nls with optim and the curve:

  

G <- function(pars) {

  pars['A'] * (1 - exp(-pars['age']*data$age))^pars['theta']

}

  

pars = c(A = 133, age = 0.02992, theta = 1.1162)

  

nls <- function(pars) {

  sum((G(pars) - data$agbd)^2)

}

  

o = optim(par = pars, fn = nls)

o

  

plot(data$age, data$agbd)

curve( 87.07455636 * (1 - exp(-0.07435007*x))^1.69029407, add = TRUE)

# that's starting from the values given by NLS.

# if we start with values a bit off, it doesn't work anymore:

# starting with:

pars = c(A = 100, age = 1, theta = 1)

o = optim(par = pars, fn = nls)

o

# now the likelihood is 18604, rather than 2612.

# starting with age=0.5, it works again.

# so I guess we gotta try a bunch of different starting values.

  

# trying NLL with her functional form (no intercept, with a delay term)

  

#let's investigate why NLL breaks, making zeroes.

  

G <- function(pars) {

  pars['A'] * (1 - exp(-pars['age']*data$age))^pars['theta']

}

  

NLL = function(pars) {

   if(pars['age'] > 0.5){

     return(-Inf)

   }

  if(pars['age'] < -0.5){

     return(-Inf)

   }

  # Negative log-likelihood

  print(-sum(dnorm(x = data$agbd - G(pars), mean = 0, sd = 0.05, log = TRUE), na.rm = TRUE))

}

  

pars = c(A = 133, age = 0.02992, theta = 1.1162) #, sd = 0.05)

#pars = c(A = 87.07455636, age = 0.07435007, theta = 1.69029407) #, sd = 0.05)

  

o = optim(par = pars, fn = NLL)

o

  

G(o$par)

  

sum((G(o$par) - data$agbd)^2)

  

-sum(dnorm(x = data$agbd - G(o$par), mean = 0, sd = pars['sd'], log = TRUE))