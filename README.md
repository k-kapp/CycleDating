# CycleDating

Algorithms designed to optimise the following problem, were developed in the MSc thesis:

Maximise

<p align="center">
<img src="Formula.png">
</p>

subject to

<p align="center">
<img src="Formula.png">
</p>

An optimal solution to the problem above can be interpreted as optimal times to buy and sell a given asset, disregarding transaction costs. Cycles of buy-sell times are therefore found. An example is shown below, where red dots represent the near-optimal buy-sell points found.

<p align="center">
<img src="CycleDatingExample.png" width="550">
</p>


A final solution also has the ability to effectively represent a time series with much less observations than the original time series. Consider a time series of 16000 observations:

<p align="center">
<img src="OrigSeries.png" width="550">
</p>

Now, if we extract 160 buy-sell points, and represent the time series only with those 160 points:

<p align="center">
<img src="Reduced160Points.png" width="550">
</p>

Represented with 80 points:

<p align="center">
<img src="Reduced80Points.png" width="550">
</p>

Represented with 40 points:

<p align="center">
<img src="Reduced40Points.png" width="550">
</p>

Represented with 10 points:

<p align="center">
<img src="Reduced40Points.png" width="550">
</p>

One therefore has the choice to represent the time series at varying compression rates. This may be seen as an alternative way to compress time series, than those given in Keogh et al., for example.

A short description of each algorithm is given below.

### BSA-Extrema Importance Identity sequence retrieval (BSA-EIISR)

This is based on the EIISR algorithm introduced by Wu and Huang (2009). It first finds candidate observations that may be used as troughs, then finds optimal peaks, given those troughs, via a simpler procedure.

### Stochastic Generation and Adaptation method  (SGA)

This method finds optimal points via a coordinate ascent approach. Very fast, but often gives more sub-optimal solutions.

### Particle Swarm Optimisation (PSO)

A stochastic search method based on swarm behaviour of animals. Was used as a benchmark in the thesis. It did not perform as well as the other algorithms.

### BSA-Bottom-up  (BSA-BU)

This method works similarly to the bottom-up method presented in Keogh (2001). All peaks and troughs are initially assumed to be buy-sell points, and are eliminated based on how little they contribute to a high value for the objective function.

### Hierarchical method

A method presented by my supervisor, also used for comparison. Was outperformed by BSA-EIISR, BSA-BU and SGA.

