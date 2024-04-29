# Two-Level Multigrid Algorithm
Implementation of the two-level multigrid algorithm applied to elliptic heat diffusion in a 1 dimensional pipe with a Dirichlet and Neumann boundary conditions.
Jupyter notebook.

# Requirements
Numpy 1.26.0
Matplotlib 3.8.4

# Setting up the Problem
Under the section "running the problem", you can find the chunks which define and discretize the system, and then generate the assembly matrix A over the fine grid. Here the pipe runs from $x=0$ and $x=1.0$, with a refinement of 0.01. The coarse grid will simply have refinement 0.02. One need not know FVM or conservation equation in fluid mechanics: a general intuition of the diffusion of heat does help. All input data for the multigrid algorithm is generated here. No outside files are needed.

# Running the Algorithm
Under the section "Multigrid Algorithm", you can find the chunks defining the multigrid algorithm. These include generating the restriction matrix, running the algorithm (this should take about 5 minutes to run), and viewing the residuals generated during execution. The algorithm returns no outputs (the exact solution will be generated, but this is not explicilty the job of the multigrid algorithm); instead correctness depends on the algorithm a) terminating and b) terminating in less iterations than the naive approach.
# Analysis
Under the "analysis" section, one can run the naive approach (this should take about 10 minutes to run) and plot the 2-norm of the residuals per iteration for both the naive (yellow) and multigrid (blue) approaches. The tolerance threshold is set to 1e-10, thus convergence is considered achieved when the 2-norm of the resdiual is below 0.0000000001. This visually confirms the correctness (and relative efficiency) of the two-level multigrid method.
