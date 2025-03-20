---
layout: page
title: "A bivariate beta distribution"
description: "Study of the bivariate beta distribution proposed by Olkin and Trikalinos (2015), parameter inference and diagnostics."
img: assets/img/alpha_solution_existence.png
importance: 1
category: Master
---

This work started with the bivariate beta distribution introduced by [Olkin & Trikalinos (2015)](https://www.sciencedirect.com/science/article/pii/S0167715214003241). 
This is a distribution is defined on $$[0,1]^2$$, has beta-distributed marginals, correlation over the full range $$(-1,1)$$ and has only four parameters.
In this work we give a full statistical treatment of this distribution, including method-of-moments estimation, Bayesian estimation and, importantly, diagnostics. 
We provide a complete treatment of the estimation problem, including classical (frequentist) and Bayesian approaches to estimation in the form of method-of-moments and latent variable/data augmentation coupled with Hamiltonian Monte Carlo, respectively. 
Elicitation of bivariate beta as a prior distribution is tackled as well. 
Using simulations and some asymptotic theory, we explore in depth an important but often neglected topic, namely the development of diagnostics for checking model fit and adequacy.
The product was an unpublished paper, with the available preprint [here](https://arxiv.org/pdf/2303.01271.pdf).

## Abstract

Correlated proportions appear in many real-world applications and present a unique challenge in terms of finding an appropriate probabilistic model due to their constrained nature. 
The bivariate beta is a natural extension of the well-known beta distribution to the space of correlated quantities on $$[0,1]^2$$. 
Its construction is not unique, however. 
Over the years, many bivariate beta distributions have been proposed, ranging from three to eight or more parameters, and for which the joint density and distribution moments vary in terms of mathematical tractability. In this paper, we investigate the construction proposed by Olkin & Trikalinos (2015), which strikes a balance between parameter-richness and tractability. 
We provide classical (frequentist) and Bayesian approaches to estimation in the form of method-of-moments and latent variable/data augmentation coupled with Hamiltonian Monte Carlo, respectively. 
The elicitation of bivariate beta as a prior distribution is also discussed. 
The development of diagnostics for checking model fit and adequacy is explored in depth with the aid of Monte Carlo experiments under both well-specified and misspecified data-generating settings. 

[Github repository](https://github.com/lucasmoschen/bivariate-beta/)