---
layout: page
title: Research
description: Dan Simpson's research
---

<b>All of my papers can be found on my [Google Scholar page](https://scholar.google.co.uk/citations?user=oQIKmWUAAAAJ&hl=en) and most are available on [arXiv](https://arxiv.org/search/advanced?advanced=&terms-0-operator=AND&terms-0-term=Daniel+Simpson&terms-0-field=author&classification-physics_archives=all&classification-statistics=y&date-filter_by=all_dates&date-year=&date-from_date=&date-to_date=&size=50&order=-announced_date_first). </b>


## Summary of contributions


Throughout my career, my research has been inspired by the problems in spatial statistics. Datasets with a spatial or spatiotemporal components are increasingly being collected in fields as diverse as ecology, epidemiology, atmospheric science, fisheries science, and forestry. The main challenge emerging is the increasing size of modern datasets: bringing about a corresponding increase in the complexity of the associated statistical models. In this environment, there is a natural attraction to Bayesian (and particularly hierarchical) modelling, which provides a framework for building increasingly complex models.

The fundamental idea of Bayesian statistics is that there is a unique, principled way to update a probabilistic model in the presence of new information. The success of this update depends on the quality of the prior probabilistic model, and for a large number of problems in applied statistics, there is no guidance on how to specify these prior probabilities. Furthermore, there are few tools that allow non-expert statisticians to validate their computational method or their models either before or after encountering data (Gelman et al., 2017). The ambition of my research program has been to fill this gap for spatial models. More abstractly, I have primarily worked with the class of Latent Gaussian Models (LGMs), which is a flexible class of models that generalize Generalized Linear Models, Multilevel models, and any model with a correlated Gaussian random effect.

My early work focused on extending the [R-INLA](http://r-inla.org/) open source software for performing fast approximate inference on LGMs (Martins et al. 2013; Rue et al. 2017). My work particularly focused on improving the spatial capabilities of the R-INLA software (Simpson et al. 2012a, 2012b, 2016; Hu et al. 2013a, 2013b, 2015; Fuglstad et al. 2015a, 2015b; Bakka et al. 2018, 2019; Krainski et al. 2019). The tight integration between my research and the R-INLA user community has enabled me to focus on moving beyond individual research projects and attempt to develop a holistic “best practice” workflow in order to furnish applied statisticians with the computational and modelling tools they need to solve practical problems.  

This desire to develop workflows for the R-INLA and [Stan](http://mc-stan.org/) communities has pushed my research beyond its initial focus on spatial models. I now have a significant body of research on modern methods for specifying (Simpson et al. 2016; Riebler et al. 2016; Fuglstad et al. 2018), interrogating (Gabry et al. 2018; Sørbye et al. 2018; Gelman et al. 2017), and justifying weakly informative prior distributions on parameters in LGMs. This aim has also inspired my recent research into visualization (Gabry et al. 2018; Vehtari et al. 2019a) and computational diagnostics (Yao et al. 2018; Talts et al. 2018; Vehtari et al. 2019a).


### Key papers: Spatial Modelling

<u>Daniel Simpson, Janine Illian, Finn Lindgren, Sigrunn Sørbye and Håvard Rue. (2016). Going off grid: Computationally efficient inference for log-Gaussian Cox processes. Biometrika. 103(1): 49--70.  </u>

This paper, incidentally one of the longest that Biometrika has ever published, has several major technical and practical contributions. Fundamentally, the paper re-considers the standard computational approximation of the log-Gaussian Cox process (LGCP) model. The aim of this was to find a form of the approximation that was better suited to finite dimensional Gaussian random fields (that is, random fields that are specified from a finite set of basis functions) such as those produced with the Stochastic Partial Differential Equation (SPDE) method of Lindgren et al. (2011). To do this, we applied direct quadrature to the LGCP likelihood. I then used theory from the inverse problems literature to bound the error in posterior computed using this approximate likelihood. This error bound contained an explicit rate, and as a corollary I derive the explicit rate for the convergence of the standard approximation, which was possibly an order of magnitude slower than our new approximation. A second major contribution to this paper was to provide explicit bounds on the convergence of the SPDE method in terms of the GRF being approximated and the approximation properties of the basis functions. This was a conclusion of the work we began in Simpson et al. (2012a-b).

<u>Geir-Arne Fuglstad, Daniel Simpson, Finn Lindgren, and Håvard Rue. (2018). Constructing Priors that Penalize the Complexity of Gaussian Random Fields. Journal of the American Statistical Association. Volume 114(525), pp. 445–452.</u>

This paper, written with my PhD student Geir-Arne Fuglstad, is the first investigation into principled prior distributions for Gaussian random fields (or Gaussian processes) in 3 or fewer dimensions that is broadly applicable. The only previous work on this topic was a mathematically and computationally difficult method for setting reference priors for a very small set of models that use Gaussian random fields. As well as using the PC prior framework to construct weakly-informative priors for the hyper-parameters, we also use appropriate asymptotic approximations to avoid complex and expensive design dependence in the resulting priors.

<u>Haakon Bakka, Håvard Rue, Geir-Arne Fuglstad, Andrea Riebler, David Bolin, Elias Krainski, Daniel Simpson, and Finn Lindgren (2018). Spatial modelling with R-INLA: A review. WIRE Computational Statistics. Volume 10(6).</u>

<u>Elias T. Krainski, Virgilio Gómez-Rubio, Haakon Bakka, Amanda Lenzi, Daniela Castro-Camilo, Daniel Simpson, Finn Lindgren and Håvard Rue. (2019) Advanced Spatial Modeling with Stochastic Partial Differential Equations Using R and INLA. CRC/Tayor and Francis Group.</u>

 This review paper and book are written by the research group that introduced both the SPDE method for scalable spatial modelling and the R-INLA software for fast approximate inference. They show the breadth of our work on this topic and demonstrate the ways that we have worked to make our research outputs available to the wider spatial modelling community.

### Key papers: Bayesian modelling, prior distributions, and workflow

<u>Daniel Simpson, Håvard Rue, Thiago Martins, Andrea Riebler, and Sigrunn Sørbye,. (2017). Penalising model component complexity: A principled, practical approach to constructing priors (with Discussion). Statistical Science. 32(1): 1-28.</u>

This paper proposes Penalised Complexity (PC) priors, a bold new framework for specifying prior distributions for Bayesian models. This is one of very few frameworks for building prior distributions from a fixed set of mathematical principle and, as such, the paper has been carefully discussed both in the four invited discussions published by Statistical Science and in the broader literature.

The PC prior framework is the first comprehensive prior specification method aimed at the types of Bayesian models that are seen in modern applications. As such, this is a broad-reaching, high-impact contribution to the literature. In the year since its this publication, PC priors have been derived an applied in a whole variety of situations. PC priors now exist for models of tail dependence for extreme data, the Hurst parameter for fractional Gaussian noise, the degrees of freedom for P-splines, parameters in the Matérn covariance function, the correlation parameter in bivariate meta-analysis models, the autoregressive parameters in an AR(p) process, and the variance in the mean-variance parameterization of the Beta distribution.

<u>Jonah Gabry, Daniel Simpson (Joint first author), Aki Vehtari, Michael Betancourt, and Andrew Gelman (2018).  Visualization in Bayesian workflow (with Discussion). Journal of the Royal Statistical Society Series A. Volume 182(2), pp. 389–402.</u>

This paper set out ways in which visualizations should be used throughout the full Bayesian workflow, from model specification, through computation, and to model checking and expansion. The paper puts particular emphasis on using prior predictive simulations to assess the assumptions that have been built into the model.

<u>Yuling Yao, Aki Vehtari, Daniel Simpson, and Andrew Gelman. (2018). Using stacking to average Bayesian predictive distributions (with discussion). Bayesian Analysis. 13(3). 917–1007</u>

This paper proposed an efficient method for combining predictive distributions that we have a bag of samples from. This method chose model averaging weights that minimize the leave-one-out log-score for the predictive density, which was computed efficiently using a recent version of importance sampling. We showed that stacking frequently performs better than Bayesian model averaging. We also proposed corrected pseudo-BMA+ model weights that are cheap to compute and approximate the stacking weights better than alternatives.


### Key papers: Computational statistics

<u>Vehtari, Aki, Daniel Simpson, Andrew Gelman, Yuling Yao, and Jonah Gabry. "Pareto smoothed importance sampling." arXiv preprint arXiv:1507.02646 (2019b). </u>

Pareto Smoothed Importance Sampling (PSIS) is a method for stabilizing importance sampling weights by modelling the extreme weights using an appropriate Pareto distribution. PSIS was initially proposed by Aki Vehtari, Andrew Gelman, and Jonah Gabry, my contribution to the manuscript was to derive theoretical convergence results that justify and extend the results in their extensive computational experiments. Due to the complicated nature of the algorithm, this was quite a complex task involving some detailed properties of order statistics. We also made a theoretical justification for a computationally derived heuristic that is useful for working out when the PSIS approximation is reliable.

<u>Aki Vehtari, Andrew Gelman, Daniel Simpson, Bob Carpenter, Paul Bürkner
(2019a). Rank-normalization, folding, and localization: An improved \widehat{R} for assessing convergence of MCMC. arXiv:1903.08008.</u>

This paper improves the R-hat diagnostic for assessing the convergence of a Markov chain originally proposed by Gelman and Rubin in 1996. Our new version greatly improves the original and is sensitive to more of the ways a Markov chain can fail to converge. We also proposed novel graphical summary of the Markov chains that give more detailed information about how reliable the computed chain is for computing various expectations.

<u>Yuling Yao, Aki Vehtari, Daniel Simpson, Andrew Gelman (2018). Yes, but did it work?: Evaluating variational inference. ICML2018.  arXiv:1802.02538.</u>

<u>Sean Talts, Michael Betancourt, Daniel Simpson, Aki Vehtari, Andrew Gelman (2018). Validating Bayesian Inference Algorithms with Simulation- Based Calibration. arXiv:1804.06788.</u>

The first paper attempts to answer the titular question for variational inference (VI) methods. Although there has been a lot of work on theoretical convergence of VI methods, there is a lack of good, computable, reliable diagnostics to check if the approximate posterior is close enough to the target posterior to be used in its place. We proposed two methods: one based on importance sampling that utilizes our work on PSIS and one based on the statistical properties of parameter recovery from simulated data (see  Talts et al. 2018). The first of these methods indicates that VI is often not a good approximation to the true posterior. On the other hand, the second diagnostic can be used to assess if the centre of the variational approximation is a good approximation to the centre of the posterior.


### Key papers: Applied research
<u>Thomas, Matthew L., Gavin Shaddick, Daniel Simpson, Kees de Hoogh, and James V. Zidek. "Data integration for high-resolution, continental-scale estimation of air pollution concentrations." arXiv preprint arXiv:1907.00093 (2019).</u>

<u>Gavin Shaddick, Matthew Thomas, Heresh Amini, David Broday, Aaron Cohen, Joseph Frostad, Amelia Green, Sophie Gumy, Yang Liu, Randall Martin, Annette Prüss-Üstün, Daniel Simpson, Aaron van Donkelaar, and Michael Brauer (2018). Data integration for the assessment of population exposure to ambient air pollution for global burden of disease assessment. Environmental Science & Technology. Volume 52(16), pp. 9069–9078. </u>

<u>Michela Cameletti, Finn Lindgren, Daniel Simpson, and Håvard Rue. (2013). Spatio-temporal modelling of particulate matter concentration through the SPDE approach. AStA Advances in Statistical Analysis. 97(2): 109-131</u>

My applied work has focused mainly on using the methods that I have developed in both spatial statistics and computational statistics to estimate air pollution on multiple spatial and temporal scales. This work is ongoing, with work in the pipeline combining SPDE methods with complex multilevel models to deal with the inhomogenous global coverage of air pollution modelling. The long-term goal will be extending these methods to properly model
1.	the multi-scale spatial and temporal nature of the process,
2.	the severe inhomogeneities in both spatial and temporal coverage of ground monitor stations,
3.	the error in satellite data products, especially when moving to space-time estimates,
4.	dealing with measurement error in the ground monitors,
5.	dealing with non-random placement of monitoring sites (the so-called preferential sampling problem).

<u><b>Watch this space</b></u> for some exciting new applied work on cause of death estimation coming in the next six months!



<!--
#### <u>The effects of increased eye contact on feeding portions</u>
*In this paper I estimate the effect of increased eye contact on the size of feeding portions delivered by my humans. Over a period of several months I varied the amount of time I spent in locked eye contact with my masters while secretely recording the total amount of food provided each day. The results incidate that the relationship between eye contact and portion size is concave, in that as eye contact increases, the portion size increases up until a point where it begins to decrease. Future research will examine whether time spent cuddling exhibits a similar relationship.*

[click here for the most recent version of the paper]({{ BASE_PATH}}/pages/working_papers/sample-working-paper.pdf)
.-->

<!-- Note: this is how to write a comment in HTML. Everything in here won't show up on your webpage.-->

<!--
To increase the size of the title, use fewer # in front of the paper title.
To decrease the size of the title, use more #.
To remove the italics, remove the * before and after the description
To remove the underline from the title, remove the <u> tags (<u> and </u>)
-->
