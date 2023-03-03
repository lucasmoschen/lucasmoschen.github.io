---
title: "Optimal Control Theory"
excerpt: "Theme of my Scientific Initiation based on the book of S. Lenhart
and J. Workman. It was developed a reference text in portuguese and notebooks
with applications in the topics."
header:
  #image: /assets/images/optimal_control_book.png
  teaser: assets/img/optimal_control_book.png
read_time: true
author_profile: true
# gallery:
#   - url: /assets/images/unsplash-gallery-image-1.jpg
#     image_path: assets/images/unsplash-gallery-image-1-th.jpg
---

## About The Project

The objective of this project is to introduce the basic concepts of Optimum
Control: existence of solution, Pontryagin Maximum Principle and Dynamic 
Programming Principle. We intend to study different formulations of a control problem, 
examples of problems in real life, specially with biologic applications, and
basic theoretical results. The main reference of the the project was the book written by Suzanne Lenhart and John T. Workman called
[Optimal Control Applied to Biological
Models](https://www.routledge.com/Optimal-Control-Applied-to-Biological-Models/Lenhart-Workman/p/book/9781584886402#:~:text=Optimal%20Control%20Applied%20to%20Biological%20Models%20thoroughly%20develops%20the%20mathematical,this%20theory%20to%20biological%20models.&text=In%20addition%2C%20the%20authors%20introduce,partial%20differential%20equations%20(PDEs).).

I could understand problems with an optimization process,
when one can control a system with some variable. For example, in the
Coronavirus Pandemic, we have a system that describes the infected,
susceptible and recovered, for example. However, the governments can interfere
this system establishing a *lockdown* or starting an immunization. 

Notes were produced on the subject in book form written in portuguese language, in order to serve as a reference in this language to start the studies in this topic. 

[[Download the book here]](https://github.com/lucasmoschen/Optimal_Control_Biological/blob/master/notes/book.pdf)

It was also developed in notebooks all the laboratories studied in these
notes. For these simulation, *Python Programming Language* associated with
*Jupyter Notebook* was used, because of its easy usage and simple
interpretation. A class in `optimal_control_class.py` file was designed to
deal with all laboratories, no need to worry with the code, initially. This
code contains the famous method in the area called forward-backward sweep.

[[The repository can be found here]](https://github.com/lucasmoschen/optimal-control-biological)

## Usage

### Notebooks 

After having the frameworks and python packages, it's necessary to open `jupyter lab` or `jupyter notebook`. In the `notebooks` folder, one can look at the Laboratories. Each laboratory is self contained, if the theory is well known. The first notebook explains the algorithm forward-backward sweep. 

- Laboratory 1: Introductory example; 
- Laboratory 2: Mold and fungicide;
- Laboratory 3: Bacteria; 
- Laboratory 4: Limited case; 
- Laboratory 5: Cancer and treatment; 
- Laboratory 6: Fish harvesting; 
- Laboratory 7: Epidemic model; 
- Laboratory 8: HIV treatment; 
- Laboratory 9: Bear population; 
- Laboratory 10: Glucose model; 
- Laboratory 11: Timber harvesting; 
- Laboratory 12: Bioreactor; 
- Laboratory 13: Predator-Prey model. 

After opening each notebook, it's easy to follow the guide. 

### Python class

If one have a optimal control problem, it can be used the Python class developed for your case. This function can handle problems with: 

- Initial conditions of the states (obliged); 
- A characterization of the control in order to update it each iteration, that is, write $$u = f(t, x, \lambda)$$ (obliged); 
- Linear payoff terms (optional); 
- Bounds in the control (optional); 
- One or several states.

After one calculate the Hamiltonian and the necessary conditions, it's necessary: 

- Differential equations for the states (if more than one state or control, the functions must return an object `numpy.array`); 
- Differential equations for the adjoint functions; 
- A characterization of the control: it can handle simple Bang-Bang problems (chapter 11) and problems with bounds; 
- Number of states and controls (optional); 

For example, in the Laboratory 8, we first define these variables 

![example1](/assets/images/example-1.png)

Because we have more than one state, we specify `n_states = 3`. We also specify the bounds. The bounds must be specified as a list of tuples for each control and `numpy.inf` is a possibility. However, the control's characterization must be written including the bounds as specified in the example. If one have a linear payoff term, it can be specified as a function: 

`diff_phi = lambda x, params: np.array([C, D, E])`. 

Observe that the parameters must be passed as a dictionary, including in the functions. At last, we define the final time and initial condition and use it in the `solve` method. 

![example2](/assets/images/example-2.png)

If one has a Bang-Bang problem, the characterization of u is given by 

`u = lambda t, x, lambda, params: a if psi(t) < 0 else b` 

Suppose we have a nonlinear payoff term or we define a final value for some state, in these cases, we do not have the final value for the adjoint corresponding to the state with that additional condition. In this case, the adapted forward-backward sweep must be used. It's not developed for so, but can be used in the following manner: one define the list `free_adj_final` with the adjoints with that characteristic. Associated with that, one make a guess passing it in `theta_list` parameter. For more details, consult the notebook 

`Chapter21-examples.ipynb`. 

## Acknowledgements

* [Fundação Getulio Vargas (FGV)]()
* [School of Applied Mathematics (EMAp)]()
* [Conselho Nacional de Desenvolvimento Científico e Tecnológico (CNPq)](https://www.gov.br/cnpq/pt-br)
* [Coordenação de Aperfeiçoamento de Pessoal de Nível Superior (CAPES)](https://www.gov.br/capes/pt-br)