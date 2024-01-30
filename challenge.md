# Challenge Statement: MIS Beyond King's Lattice
### (Based on https://arxiv.org/pdf/2307.09442.pdf)

Neutral-atom quantum hardware is well-adapted to solving maximum independent set (MIS) problems, which are known to have several applications including industries such as telecom and chip design. Previously, [studies reported](https://arxiv.org/pdf/2202.09372.pdf) a quantum speed-up of quantum adiabatic algorithms using neutral-atoms hardware against simulated annealing in graph instances of the defective king’s lattice (aka Union-Jack) class, where vertices are positioned in a square lattice with a few vertices removed randomly and connections are defined via a unit-disk constraint binding first neighbors (laterals) and second neighbors (diagonals). The king’s lattice problem instances are relevant for specific applications, in particular being [directly related](https://www.cs.du.edu/~snarayan/sada/research/docs/p130-hochbaum.pdf) to very large-scale integration (VLSI) in chip design.

More recently, the quantum speed-up against simulated annealing was more [thoroughly analyzed](https://arxiv.org/pdf/2306.13123.pdf), and conditions for performance guarantee were determined. Yet, [another work](https://arxiv.org/pdf/2307.09442.pdf) has demonstrated that more advanced classical algorithms can compute the MIS of defective king’s lattice graphs with efficiency comparable to quantum systems, solving problem instances in the order of thousands of vertices without need of specialized hardware. This sets a high bar for quantum hardware to beat, yet it introduces a silver lining. In this same work, it was also discovered that with vertices placed in a defective square grid, but with connectivity via unit-disks of order of 3 times the grid lattice constant, leads to graphs that are orders of magnitude harder for these advanced classical exact solvers. Here are some examples for you to draw inspiration from.

<p float="middle">
  <img src="/assets/Rba_sqrt2.png" width="30%" />
  <img src="/assets/Rba_3.png" width="30%" /> 
</p>
<em> (left) A defective king's lattice with vertices on a 5x5 square grid with 20% dropped-out points. Edges connect the first (lateral and vertical) and second (diagonal) neighbors. (right) A similar defective square grid, but with vertices connecting edges at a larger scale equals up to 3 times the lattice constant. </em>
</br>
</br>
Exploring this as a path for quantum advantage is your challenge!

## Activities:

### Theory
*	Determine the parameters of a quantum algorithm for a neutral atom quantum computer to solve MIS with a unit-disk radius for connectivity larger than king’s.
*	Determine if the parameters above can fit a machine like [Aquila](https://www.quera.com/aquila). If so, generate problem instances on [Bloqade](https://queracomputing.github.io/Bloqade.jl/dev/) that could be run on it.
    +	Extra points for finding if Rb/a=3 is realizable experimentally on Aquila, or what would be the best performant largest value.

### Programming
* Perform simulations using [Bloqade](https://queracomputing.github.io/Bloqade.jl/dev/) on the largest possible system sizes you can. Optimize your protocol to maximize chance of measuring an MIS (optimization methods include [Nelder-Mead](https://queracomputing.github.io/Bloqade.jl/dev/tutorials/5.MIS/main/), [Bayesian methods](https://arxiv.org/pdf/2305.13365.pdf), counter-diabatic methods, or more)
    + Demonstrating higher probability of measuring MIS => more points!
    + Being able to simulate larger systems => more points!
*	Use [generic tensor networks](https://github.com/QuEraComputing/GenericTensorNetworks.jl), [Bloqade](https://queracomputing.github.io/Bloqade.jl/dev/), or your favorite method to estimate the (quantum and classical) annealing hardness parameters of the problem instances you found
    + Finding harder instances => more points!
*   Run jobs of comparative problem instances on Aquila with algorithm of choice and analyze data (no hybrid closed-loop optimization is allowed, so just use classically optimized controls)
    + Larger problems and better chance to solution => more points

### Business
*   Determine an application for MIS in the areas of energy (e.g., power grid networks), biology/health, logistics, or finance.
    + bonus points if your application requires graphs fitting exactly the constraint of the Rb/a=3 type
*   Estimate how many vertices would be necessary for real-life problems. 
    + Bonus points for finding applications that require order near-term numbers of qubits, order few hundreds.

While you are encouraged to play to your strengths when choosing focus on the activities above, note that the winning team will be the one with the strongest presentation all across the board! So make sure you divide your attention and efforts properly.

And to finish: don't forget to prepare a 5-10min presentation with your findings and results! Support visuals (such as slides) will be welcome. You will have an opportunity to present your results in this format during the project presentation time on Sunday.