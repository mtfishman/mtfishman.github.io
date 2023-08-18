+++
title = "Projects"
+++

# Projects

\toc

# Coding Projects

## ITensors.jl

I am the lead developer of
[ITensors.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl)
, a full port of the
[C++ ITensor library ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensor)
to the Julia language.
It is a library I co-develop with
[Miles Stoudenmire ~~~<i class="fas fa-external-link-alt"></i>~~~](http://itensor.org/miles)
for easily developing and running high performance tensor network
algorithms, with applications to quantum physics, quantum computing,
chemistry, and data science/machine learning.

[~~~<i class="fas fa-external-link-alt"></i>~~~ itensor.org](https://itensor.org)

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl)

~~~<i class="fas fa-file-alt"></i>~~~ \cite{fishman2020}

ITensors.jl news
---

~~~<i class="fas fa-newspaper"></i>~~~
__Automatic differentiation:__
Derivatives of basic tensor network operations like tensor contraction and addition
as well as many MPO/MPS operations like gate evolution using automatic
differentiation are now supported.
Reverse mode automatic differentiation (AD) primitives are defined using
[ChainRulesCore.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaDiff/ChainRulesCore.jl)
, and derivatives can be computed with AD libraries like
[Zygote.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/FluxML/Zygote.jl)
(and eventually next generation AD libraries like
[Diffractor.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaDiff/Diffractor.jl)
).

~~~<i class="fas fa-newspaper"></i>~~~
__Lazy Operator Algebra (Ops) system:__
Within ITensors.jl, we now have support for a general lazy
operator algebra system called
[Ops  ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/src/Ops)
.
This system can be used to represent arbitrary sums, products, and other
algebraic manipulations of quantum operators (or more generally linear transformations
in tensor product spaces).
This can be used to represent local Hamiltonians and quantum circuits,
as well as useful algebraic operations like expanding product of sums
of operators and representing Trotter-Suzuki decompositions to transform
exponentials of sums of operators into products of exponentials of operators.
Additionally, operator representations can then be converted into explicit
tensor representations for use in tensor network algorithms or to perform
diagonalizations.

~~~<i class="fas fa-tools"></i>~~~
The Ops systems needs testing, documentation, and automatic differentation
support.
Please [reach out](/about/#online_presence) if you are interested in helping
out!

ITensors.jl wish list
---

~~~<i class="fas fa-tools"></i>~~~
__Automatic differentiation:__
Our goal is to make the entire `ITensors.jl` package differentiable,
but currently we only have basic operations like tensor contraction,
addition, and index manipulation.
More reverse mode automatic differentation rules
(`ChainRulesCore.jl` `rrule`s) and/or modifications of internal `ITensors.jl`
functions to avoid non-differentiable code patterns like mutation are
needed to make this happen.
The following functionality is high priority:
* Differentiation rules for tensor decompositions like SVD, QR, eigendecomposition, etc. This will allow us to more directly differentiate through approximate tensor network algorithms like CTMRG for automatic differentiation-based gradient optimization of infinite projected entangled pair states (PEPS).
* Differentation rules for matrix product state (MPS) and matrix product operator (MPO) algebra operations, like contraction, addition, construction, etc.
* Differentation support for the new [Ops system ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/src/Ops), which will allow differentiating through the construction of operators and Trotter decompositions. This will make for much more robust support for variational quantum circuit applications like quantum control (though we already have initial support for that in [PastaQ.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/GTorlai/PastaQ.jl)).

~~~<i class="fas fa-tools"></i>~~~
__More block sparse multithreading:__ 
We currently support block sparse multithreaded tensor contractions.
We would like to add multithreading support to other block sparse
operations, such as addition, permutation, and decomposition.
Please [reach out](/about/#online_presence) if you are interested
in contributing code for that!

~~~<i class="fas fa-tools"></i>~~~
__More block sparse factorizations:__ 
We currently support block sparse multithreaded tensor contractions.
We would like to add multithreading support to other block sparse
operations, such as addition, permutation, and decomposition.
Please [reach out](/about/#online_presence) if you are interested
in contributing code for that!

~~~<i class="fas fa-tools"></i>~~~
__ITensor slicing:__ 
We have good support for slicing dense tensors at the level of
[NDTensors.Tensor](/projects/#ndtensorsjl), as well as slicing
a single block of a block sparse `NDTensors.Tensor`.
However, it would be helpful to have high level support for
slicing at the level of ITensors, which requires having an interface
for slicing Index objects, which could be represented by objects like
`i => 2:3` of type `Pair{Index{Int64},UnitRange{Int64}}`.
Additionally, it would be helpful to have more robust support for more
general slices of block sparse tensors, including slices across
multiple blocks and within blocks.

---

### NDTensors.jl

[NDTensors.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/NDTensors)
is the more traditional tensor algebra package underlying `ITensors.jl`.
It defines an n-dimensional tensor `Tensor` that can have a variety of
storage data types for various sparse and constrained tensors, such
as dense, block sparse, and diagonal, with more planned such as tensors
with isometric/unitary constraints.
It implements high performance operations between mixtures of different
tensor types such as addition, permutation, matrix factorization,
and contraction.
Additionally, it supports block sparse multithreaded contraction.

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl/tree/main/NDTensors)

NDTensors.jl wish list
---

~~~<i class="fas fa-tools"></i>~~~
__Tensors with isometric/unitary constraints:__ 
A special tensor storage type representing a tensor with isometric/unitary
constraints would be useful in a variety of applications, such as isometrically
constrained gradient optimization, automated simplification of tensor network
contractions involving contractions of isometric tensors, etc.
Please [reach out](/about/#online_presence) if you are interested in helping
us implement this feature.

~~~<i class="fas fa-tools"></i>~~~
__Lazy complex conjugation:__ 
It would be helpful for improving performance and memory usage to add
support for lazy complex conjugation.
For example, tensor contractions involving complex conjugation could be
mapped directly to matrix multiplication calls to BLAS without allocating
temporary complex conjugated tensors.

---

### ITensorNetworks.jl

[ITensorNetworks.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/mtfishman/ITensorNetworks.jl)
This is the next-generation general tensor network library built on top of ITensors.jl.
It will generalize the MPS solvers like DMRG, TDVP, and linear solving, as well as tools
for gate evolution, that are available in ITensors.jl and
[ITensorTDVP.jl](https://github.com/ITensor/ITensorTDVP.jl) to tree tensor
networks (TTN) and even more general tensor networks. Stay tuned for more developments!

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/mtfishman/ITensorNetworks.jl)

---

### ITensorGLMakie.jl

[ITensorGLMakie.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGLMakie) is a package I wrote for easily making interactive visualizations of tensor networks written with ITensors.jl, based on [GraphMakie.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaPlots/GraphMakie.jl) and [Makie.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaPlots/Makie.jl).
It supports clicking and dragging nodes/tensors of the tensor network.

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGLMakie)

---

~~~<i class="fas fa-tools"></i>~~~
__More interactive customization:__ 
Currently, `ITensorGLMakie.jl` only support simple interactivity, such as clicking
and dragging the nodes/tensors of the tensor network diagram.
We would like to have more interactivity, such as interactively selecting the
color, shape, and labels of the nodes/tensors.

~~~<i class="fas fa-tools"></i>~~~
__Multigraph visualization:__ 
`ITensorGLMakie.jl` currently visualizes tensors with multiple shared indices
with a single edge and a label with information about the multiple edges.
It would be helpful to directly visualize the multiple edges/indices.
`GraphMakie.jl`, the package we use as a backend for `ITensorGLMakie`,
implicitly
[supports visualizing multigraphs](https://github.com/JuliaPlots/GraphMakie.jl/issues/52)
, so support for this should be straightforward to add.

### ITensorUnicodePlots.jl

[ITensorUnicodePlots.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/ITensorUnicodePlots) is an alternative backend for visualizing networks of ITensors as text output, based on [UnicodePlots.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaPlots/UnicodePlots.jl).

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl/tree/main/ITensorUnicodePlots)

### ITensorGaussianMPS.jl

[ITensorGaussianMPS.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGaussianMPS) is a Julia package I wrote for transforming free fermion states into tensor network states, based on an algorithm I developed during my Ph.D. with [Steven White ~~~<i class="fas fa-external-link-alt"></i>~~~](https://faculty.sites.uci.edu/dmrg/).

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGaussianMPS)

~~~<i class="fas fa-file-alt"></i>~~~ \cite{fishman2015}

### ITensorInfiniteMPS.jl

[ITensorInfiniteMPS.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensorInfiniteMPS.jl) is a Julia package I wrote for extending the functionality of ITensors.jl to infinite MPS.

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensorInfiniteMPS.jl)

~~~<i class="fas fa-file-alt"></i>~~~ \cite{stauber2017}

### Other extensions to ITensors.jl

Many packages are in development that extend the functionality of ITensors.jl, such as packages for performing network level contractions and gradient optimizations of tensor networks, packages for interfacing with quantum chemistry libraries like PySCF, and more. Stay tuned and keep an eye out on my [Github page ~~~<i class="fab fa-github"></i>~~~](https://github.com/mtfishman), the [ITensor Github organization ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor), and the [ITensor website ~~~<i class="fas fa-external-link-alt"></i>~~~](https://itensor.org)!

## PastaQ.jl

[PastaQ.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/GTorlai/PastaQ.jl) is a package I co-develop with [Giacomo Torlai ~~~<i class="fas fa-external-link-alt"></i>~~~](https://github.com/GTorlai) for simulating and analyzing quantum computers, including noisy state and process simulation with customizable noise models, state-of-the-art algorithms for tomography and ongoing work using automatic differentiation to optimize quantum circuits for implementing algorithms like variational quantum eigensolver (VQE) and optimal control.

[~~~<i class="fas fa-external-link-alt"></i>~~~ pastaq.org](https://pastaq.org)

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/GTorlai/PastaQ.jl)

## ITensor (C++)

[ITensor ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensor) is a C++ library for developing and performing tensor network calculations. I was the lead developer of [C++ ITensor Version 3 ~~~<i class="fas fa-external-link-alt"></i>~~~](https://itensor.org/news.html), the latest major release of the library which had many improvements to the interface and performance of block sparse calculations, including the introduction of block sparse multithreading with OpenMP.

[~~~<i class="fas fa-external-link-alt"></i>~~~ itensor.org](https://itensor.org)

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensor)

## Miscellaneous Julia Packages

### Observers.jl

I co-developed [Observers.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/GTorlai/Observers.jl) with [Giacomo Torlai ~~~<i class="fas fa-external-link-alt"></i>~~~](https://github.com/GTorlai). It is a package for conveniently specifying a set of measurements you want to make inside of an iterative method.
It is currently being used in
[PastaQ.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/GTorlai/PastaQ.jl)
inside iterative optimization methods like quantum state and process
tomography as well as quantum circuit evolution, and we plan to make use
of it in [ITensors.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl).

~~~<i class="fas fa-tools"></i>~~~
__Using `Observers.jl` in `ITensors.jl`:__
We are interested in using
[Observers.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/GTorlai/Observers.jl)
inside iterative methods in
[ITensors.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl)
like the density matrix renormalization group (DMRG) eigensolver as well
as our circuit simulation functionality (`apply`).
Please [reach out](/about/#online_presence) to me if you are interested
in helping out with this! It would be a good project for a new user
trying to learn about DMRG, Julia, and ITensors.jl.

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/GTorlai/Observers.jl)

### SerializedElementArrays.jl

[SerializedElementArrays.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/SerializedElementArrays.jl) is a package I wrote that provides a new Julia Array type (a SerializedElementArray) whose elements are saved to disk. This can help in cases where you have collections of large contiguous data (like an Array of very large Arrays) which individually fit in memory but collectively do not. This is used for the write-to-disk feature in ITensors.jl.

## Tensor network algorithm development

### Gauging tensor networks with belief propagation and applications to circuit simulation

We recently developed a new method for gauging tensor networks based on belief propagation, and applied it to simulate the kicked transverse field Ising model on a heavy-hex lattice, a model that was recently emulated on IBM's Eagle quantum processor.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{tindall2023a}

~~~<i class="fas fa-file-alt"></i>~~~ \cite{tindall2023b}

### Gaussian circuits and impurity solvers

[Steven White ~~~<i class="fas fa-external-link-alt"></i>~~~](https://faculty.sites.uci.edu/dmrg/) and I developed an algorithm for obtaining a compact quantum circuit of local gates for a free fermion state. This leads to a straightforward way to construct tensor network state like matrix product states (MPS), tree tensor networks (TTN), and multi-scale entanglement renormalization ansatz (MERA) for free fermion states.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{fishman2015}

We have recently applied this method to develop next-generation impurity solvers based on disentangling the non-interacting bath, as well as by representing the influence matrix of the non-interacting bath as a matrix product state (MPS).

~~~<i class="fas fa-file-alt"></i>~~~ \cite{wu2022}

~~~<i class="fas fa-file-alt"></i>~~~ \cite{kloss2023}

### Variational uniform matrix product states and tree tensor networks

In collaboration with colleagues at the University of Ghent and the University of Vienna, I helped to develop a new algorithm for finding ground states of quasi-1D quantum systems directly in the thermodynamic limit, which is faster at finding ground states than the state-of-the-art alternatives. The algorithm is called the variational uniform matrix product state (VUMPS) algorithm.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{stauber2017}

In collaboration with colleagues at the CCQ, I worked on extending the VUMPS algorithm to solve for ground states of infinite tree tensor networks states, such as states on the Bethe lattices, in an algorithm we called the variational uniform tree state (VUTS) algorithm.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{lunts2020}

### Improved contraction methods for infinite 2D tensor networks

In collaboration with colleagues at the University of Ghent and the University of Vienna, I worked on extending the VUMPS algorithm to the problem of contracting infinite 2D tensor networks and showed that in many cases it outperforms the standard method, the corner transfer matrix renormalization group (CTMRG) algorithm. In addition, I worked on a fixed point formulation of CTMRG which we also showed was faster than the original CTMRG algorithm, which we called the fixed point corner method (FPCM).

~~~<i class="fas fa-file-alt"></i>~~~ \cite{fishman2017}

### Easing the sign problem with variational circuits and automatic differentation

With colleagues from CCQ and other institutions, I helped develop a method for decreasing the average sign of a wavefunction by optimizing a quantum circuit ansatz with automatic differentiation. This could have implications for improving the performance of monte carlo algorithms.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{torlai2019}

## References

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{tindall2023b}{Tindall et al. (2023)} **Tindall, Fishman** [Gauging tensor networks with belief propagation](https://arxiv.org/abs/2306.17837), 2023.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{tindall2023a}{Tindall et al. (2023)} **Tindall, Fishman, Stoudenmire, Sels** [Efficient tensor network simulation of IBM's Eagle kicked Ising experiment](https://arxiv.org/abs/2306.14887), 2023.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{kloss2023}{Kloss et al. (2023)} **Kloss, Thoenniss, Sonner, Lerose, Fishman, Stoudenmire, Parcollet, Georges, Abanin** [Equilibrium Quantum Impurity Problems via Matrix Product State Encoding of the Retarded Action](https://arxiv.org/abs/2306.17216), 2023.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{wu2022}{Wu et al. (2022)} **Wu, Fishman, Pixley, Stoudenmire** [Disentangling Interacting Systems with Fermionic Gaussian Circuits: Application to the Single Impurity Anderson Model](https://arxiv.org/abs/2212.09798), 2022.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{lunts2020}{Lunts et al. (2020)} **Lunts, George, Stoudenmire, Fishman** [The Hubbard model on the Bethe lattice via variational uniform tree states: metal-insulator transition and a Fermi liquid](https://arxiv.org/abs/2010.06543), 2020.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{fishman2020}{Fishman et al. (2020)} **Fishman, White, Stoudenmire** [The ITensor Software Library for Tensor Network Calculations](https://arxiv.org/abs/2007.14822), 2020.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{torlai2019}{Torlai et al. (2019)} **Torlai, Carrasquilla, Fishman, Melko, Fisher** [Wavefunction positivization via automatic differentiation](https://arxiv.org/abs/1906.04654), 2019.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{fishman2017}{Fishman et al. (2017)} **Fishman, Vanderstraeten, Zauner-Stauber, Haegeman, Verstraete** [Faster Methods for Contracting Infinite 2D Tensor Networks](https://arxiv.org/abs/1711.05881), 2017.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{stauber2017}{Zauner-Stauber et al. (2017)} **Zauner-Stauber, Vanderstraeten, Fishman, Verstraete, Haegeman** [Variational optimization algorithms for uniform matrix product states](https://arxiv.org/abs/1701.07035), 2017.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{fishman2015}{Fishman et al. (2015)} **Fishman, White** [Compression of Correlation Matrices and an Efficient Method for Forming Matrix Product States of Fermionic Gaussian States](https://arxiv.org/abs/1504.07701), 2015.
