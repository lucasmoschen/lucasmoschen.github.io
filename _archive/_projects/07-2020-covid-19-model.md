---
title: "Covid 19 Model"
excerpt: "Numerical simulations and applications of the model developed in the
publication mentioned in the first tab."
header:
  #image: /assets/images/covid19-model.png
  teaser: assets/img/covid19-model.png
read_time: true
author_profile: true
gallery:
  - url: /assets/images/infectious_website.png
    image_path: /assets/images/infectious_website.png
    alt: "cumulative infectious curve"
  - url: /assets/images/deaths_website.png
    image_path: /assets/images/deaths_website.png
    alt: "cumulative death curve"
---

Numerical simulations and applications of the model described in the
publication entitled [*A model for COVID-19 with isolation, quarantine and
testing as control measures*](https://doi.org/10.1016/j.epidem.2021.100437), a publication
that I was co-author. 

In addition to the model description, the article shows, in the fourth
chapter, numerical simulations to test the model and make some appointments
about the disease, in special about the non-pharmaceutical control measures
isolation, quarantine and testing. The model and the simulations were written
in *Python* language. 

[See the repository here](https://github.com/lucasmoschen/covid-19-model)

In the
[README](https://github.com/lucasmoschen/covid-19-model/blob/master/README.md),
it's possible to understand how to use the model after changing the desired
parameters. In order to generate the scenarios in the article, it's pretty
easy, because of the script designed only for that: `scenarios.py`. 

Any suggestions of improvement are welcome, specially in the graphics, since
the code is not developed yet for that purpose. 

Example
---

As example, I shall generate a simple scenario considering how the change in
testing can affect the disease behavior. We consider it in Scenario E in the
article. We expect to see a positive effect when the testing is higher among
the population. We will consider the following parameters: 

|Parameter|Meaning|Value|Reference|
|---------|-------|-----|---------|
|$$\beta$$|transmission rate (*) |$$1.0$$|arbitrary in the range (article)|
|$$r$$|reduction coefficient of transmission for people in social distance (*) |$$\begin{cases} 1, &t \le 31 \\ 0.2, &t > 31\end{cases}$$|scenario A (article)|
|$$p$$|proportion of the population in volunteer isolation (*)|$$\begin{cases} 0, &t \le 31 \\ 0.9, &t > 31\end{cases}$$|scenario A (article)|
|$$\tau$$|inverse of the latent time|$$1/3.2$$|article|
|$$\sigma$$|inverse  time from infectiousness onset to possible symptoms onset|$$1/2$$|article|
|$$\alpha$$|proportion of undetected infectious|$$0.91$$|[this estimation](https://www.scielo.br/scielo.php?pid=S0103-507X2020000200224&script=sci_arttext&tlng=en)|
|$$\gamma_1$$|recovery rate for mild cases|$$1/8$$|article|
|$$\gamma_2$$|recovery rate for severe cases|$$1/16$$|article|
|$$\mu$$|mortality rate among confirmed cases|$$0.058/14$$|scenario A (article)|
|$$\delta$$|probability of detection by testing in latent period|$$0.8$$|arbitrary|
|(*) may vary with time|

Also we have the testing rate $$\rho$$ and it will vary from the values:
$$0.01, 0.03, 0.05$$ and $$0.1$$. 

It's important to note the relation between the parameters $$\mu$$ and
$$\rho$$. If $$\rho$$ is high, we expect an increase of confirmed cases
(compartment $$Q$$). If $$\mu$$ is fixed, it will raise the deaths, as well.
In this case, we note a relation between those parameters, not studied in the
article. 

However, when $$\rho$$ parameter changes little, we expect $$\mu$$ varies
little too. 

#### Using the Python script


1. Open the file `parameters.yaml` and change the values as above: The
   parameter `change_p` is reserved for the date when $$p$$ changes. In this
   case, it will be $$31$$.
2. Change the variable functions ($$r, \rho, \beta)$$ in the class `Parameters_Functions` in
   `dynamics_model.py` file. 
3. Run `python execute_model.py`. Follow the instructions to save the variables in the terminal. 

The graphics were generated in the notebook `graphics_website.ipynb`. 

{% include gallery caption="This is a sample gallery to go along with this
numerical simulation." %}

The parameter $$\rho$$ indicates the proportion of the population presenting either mild or no symptoms that is tested daily. It can also be thought as the
inverse of the mean duration that an infected person in compartments A passes without being tested.

Estimation of the underreporting rate of COVID-19 cases in the city of Rio de Janeiro.
--- 

The COVID-19 disease caused by the SARS-CoV-2 virus has been spreading rapidly
over the world since the beginning of 2020. The understanding of its dynamics
in the population is crucial to take measures that contain the spread. In this
report, we consider the epidemiological model SEIAQR aforementioned to
understand the beginning of the epidemic in the city of Rio de Janeiro and, in
particular, the underreporting rate, that is, the proportion of infected
individuals that the system didn't register. The curves of confirmed cases and
deaths were adjusted to the actual city data using the error-weighted least
squares method. We use B-splines to approximate the transmissibility and
mortality of the disease. Also, we analyze the structural and practical
identifiability of the model to verify the feasibility of the estimates. We
used the Bootstrap method to quantify the uncertainty about the parameter's
estimates. In the period March-July 2020, we obtain the point estimate of 0.9
for underreporting with a 95 % confidence interval (0.85, 0.93). 

The details can be found in a portuguese report for my scientific initiation
[here](https://github.com/lucasmoschen/covid-19-model/blob/master/notes/underreporting_estimation.pdf).