- Distribuição Chi-Square, Student t-test, Fisher-Snedecor F 


Chi squared

[A. Jordan Nafa on Twitter: "Do people outside of elementary statistics courses do χ2 tests? Like, is that an actual thing?" / X](https://twitter.com/ajordannafa/status/1599274821832974336)

Porque p-values não são tudo isso:
[The p‐value statement, five years on - Matthews - 2021 - Significance - Wiley Online Library](https://rss.onlinelibrary.wiley.com/doi/full/10.1111/1740-9713.01505)

[(1) Matt Dancho (Business Science) on X: "This used to be me when I was first learning linear regression. 😂 But here's what's changed for me. https://t.co/ToTbP3hjZv" / X (twitter.com)](https://twitter.com/mdancho84/status/1626709235282202629)

![[FpM6vlmXEAM5mwp.jpeg]]


Why p-values should be interpreted as p-values and not as measures of evidence

Lakens, 2022

no arbitrary general measures of significance will apply to all studies. Consider the specificities of each sample and effect size.

What was done?

Muff et al (2021):

- statistical significance (binary)

- Fisher had said to include it as a determination of what values need “closer investigation” - not to be used for automatic inference

- evidence (gradual)

“If the null-hypothesis is true, p-values are uniformly distributed. This means it is just as likely to observe a p-value of 0.001 as it is to observe a p-value of 0.999. This indicates that the interpretation of p = 0.001 as ‘strong evidence’ cannot be defended just because the probability to observe this p-value is very small. After all, if the null hypothesis is true, the probability of observing p = 0.999 is exactly as small.”

The evidential value of a single p-value depends on the statistical power of the test (i.e., on the sample size in combination with the effect size of the alternative hypothesis).

effect size → how different the alternative is from the null.

If the alternative hypothesis is true the strength of evidence that corresponds to a p-value depends on the statistical power of the test.

Paper's conclusions

Indeed binary statistical significance isn’t great, but then again neither is having a standard scale for the p values “evidence” because it all depends.

In other words, whether or not we can reject a statistical hypothesis in a specific experiment does not necessarily inform us about the truth of the theory. Decisions about the truthfulness of a theory requires a careful evaluation of the auxiliary hypotheses upon which the experimental procedure is built

Although it is true that an alpha level of 0.05 is arbitrary, there are some pragmatic arguments in its favor (e.g., it is established, and it might be low enough to yield claims that are taken seriously, but not high enough to prevent other researchers from attempting to refute the claim, see Uygun Tunç et al., 2021).

Given that coherent alternatives exist, such as likelihoods (Royall, 1997) or Bayes factors (Kass & Raftery, 1995), researchers should not follow the recommendation by Muff and colleagues to report p = 0.08 as ‘weak evidence’, p = 0.03 as ‘moderate evidence’, and p = 0.168 as ‘no evidence’.

Bayes factors represent the relative probability assigned to the observed data under each of the competing hypotheses.