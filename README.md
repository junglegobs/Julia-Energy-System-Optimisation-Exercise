# Julia Energy System Optimisation Exercise

Your task:

* Complete `exercise.jl` to include the economic dispatch optimisation problem (mathematical description below).
* Calculate and report the expected energy not served (definition below) for 10 samples.

It also tests whether your general coding skills, e.g. ability to install and use Julia, Git, ...

You may find the following resources useful:

* [Getting started with Julia and JuMP](https://jump.dev/JuMP.jl/stable/tutorials/getting_started/getting_started_with_julia/)
* [ESIM Advanced Julia Trainaing](https://gitlab.kuleuven.be/UCM/esim-advanced-julia-training)

An economic dispatch problem looks like:

$$
\min \sum_{g \in G} c_g \cdot q_{g,t} + VOLL \cdot ls_{t} \\ 
s.t. \\
\sum_{g \in G} q_{g,t} = D_t - ls_t \quad \forall t \in T \\
q_{g,t} \leq AF_{g,t} \cdot cap_g \quad \forall g \in G, \; t \in T 
$$

where:

* `q_{g,t}` is the energy generated by generator `g` at time step `t`
* `ls_t` is the load shed / energy not served at time step `t`
* `cap_g` is the capacity of generator `g`
* `AF_{g,t}` is the availability of generator `g` at time step `t`
* `c_g` is cost of provided a unit of energy by generator `g`
* `VOLL` is the value of lost load i.e. the cost of not serving energy

The energy not served for one instance of the economic dispatch problem is given by:

$$
ENS = \sum_{t \in T} ls_t
$$

The expected energy not served for `n` instances of the economic dispatch problem is given by:

$$
EENS = \frac{1}{n} \sum_{i = 1:n} \sum_{t \in T} ls_t
$$
