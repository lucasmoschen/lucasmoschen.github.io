---
layout: page
title: "Network analysis of the Chamber of Deputies"
description: "Network science tools to analyze the Brazil's Chamber of Deputies considering the 
              voting pattern."
img: assets/img/network-science.png
importance: 2
category: 2021
---

[GitHub's repository](https://github.com/lucasmoschen/project-network-science).

The Brazilian Chamber of Deputies is one of the two houses of the National Congress of Brazil, alongside the Federal Senate. It is composed of 513 members, who are elected every four years through a proportional representation system. The main function of the Chamber of Deputies is to represent the Brazilian people and pass legislation, including the national budget and other important bills. Overall, the Chamber of Deputies plays a crucial role in the Brazilian political system, as it is responsible for ensuring that the voices of the people are heard and that their interests are represented in the government.

To stand for election, it is mandatory to be a member of a party.
With 33 registered parties, Brazil is the country with the largest number of political parties in the world.
The composition from 2019 to 2022 is the following:

<center>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/25/C%C3%A2mara_dos_Deputados_do_Brasil_em_2023.svg/1200px-C%C3%A2mara_dos_Deputados_do_Brasil_em_2023.svg.png" width=400px>
</center>

In Brazil, a proposition can become a law through a multi-step process that involves both the legislative and executive branches of government. 
The process starts when a proposal is introduced in either the Chamber of Deputies or the Senate. 
After the proposal is debated, amended, and approved by both houses of Congress, it is sent to the President for signature.
If the President signs the proposal, it becomes law.
Once a proposition becomes law, it is published in the official gazette, which is the government's official record of all legal acts. 
The law then goes into effect and is enforced by the appropriate government agencies.

The voting data from the Chamber of Deputies is publicly available through the Python package [DadosAbertosBrasil](https://pypi.org/project/DadosAbertosBrasil/).
From that, we extracted information from 2003 to 2021 about the deputies, their voting patterns and their propositions.
From this dataset, we built a network where the nodes are the deputies and the links represent the voting pattern similarity.

For more details and results, consult the Github repository and the [PDF presentation](https://github.com/lucasmoschen/project-network-science/blob/main/notes/project-presentation.pdf).