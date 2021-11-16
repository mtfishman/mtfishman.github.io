+++
title = "Projects"
+++

# Projects

\toc

# Coding Projects

## ITensors.jl

I am the lead developer of [ITensors.jl](https://github.com/ITensor/ITensors.jl), a full port of the [C++ ITensor library](https://github.com/ITensor/ITensor) to the Julia language.

### ITensorsVisualization.jl

[ITensorsVisualization.jl](https://github.com/ITensor/ITensorsVisualization.jl) is a package I wrote for easily making interactive visualizations of tensor networks written with ITensors.jl.

### ITensorGaussianMPS.jl

[ITensorGaussianMPS.jl](https://github.com/ITensor/ITensorGaussianMPS.jl) is a Julia package I wrote for transforming free fermion states into tensor network states, based on an algorithm I developed during my Ph.D. with [Steven White](https://faculty.sites.uci.edu/dmrg/).

### ITensorInfiniteMPS.jl

[ITensorInfiniteMPS.jl](https://github.com/ITensor/ITensorInfiniteMPS.jl) is a Julia package I wrote for extending the functionality of ITensors.jl to infinite MPS.

### ITensorsGPU.jl

[ITensorsGPU.jl](https://github.com/ITensor/ITensorsGPU.jl) isa a GPU backend for ITensors.jl primarily written by [Katie Hyatt](https://github.com/kshyatt) while she was a postdoc at the CCQ.

### Other extensions to ITensors.jl

Many packages are in development that extend the functionality of ITensors.jl, such as packages for performing network level contractions and gradient optimizations of tensor networks, packages for interfacing with quantum chemistry libraries like PySCF, and more. Stay tuned and keep an eye out on the [my Github page](https://github.com/mtfishman) and [the ITensor Github organization](https://github.com/ITensor)!

## PastaQ.jl

[PastaQ.jl](https://github.com/GTorlai/PastaQ.jl) is a package I co-develop with [Giacomo Torlai](https://github.com/GTorlai) for simulating and analyzing quantum computers, including noisy state and process simulation with customizable noise models, state-of-the-art algorithms for tomography and ongoing work using automatic differentiation to optimize quantum circuits for implementing algorithms like variational quantum eigensolver (VQE) and optimal control.

## ITensor (C++)

[ITensor](https://github.com/ITensor/ITensor) is a C++ library for developing and performing tensor network calculations. I was the lead developer of ITensor V3, the latest major release of the library which had many improvements to the interface and performance of block sparse calculations.

## Miscellaneous Julia Packages

### Observers.jl

I co-developed [Observers.jl](https://github.com/GTorlai/Observers.jl) with [Giacomo Torlai](https://github.com/GTorlai). It is a package for conveniently specifying a set of measurements you want to make inside of an iterative method.

### SerializedElementArrays.jl

[SerializedElementArrays.jl](https://github.com/ITensor/SerializedElementArrays.jl) is a package I wrote that provides a new Julia Array type (a SerializedElementArray) whose elements are saved to disk. This can help in cases where you have collections of large contiguous data (like an Array of very large Arrays) which individually fit in memory but collectively do not. This is used for the write-to-disk feature in ITensors.jl.

## Tensor Network algorithm development

### Free Fermion Tensor Networks

[Steven White](https://faculty.sites.uci.edu/dmrg/) and I developed an algorithm for obtaining a compact quantum circuit of local gates for a free fermion state. This leads to a straightforward way to construct tensor network state like matrix product states (MPS), tree tensor networks (TTN), and multi-scale entanglement renormalization ansatz (MERA) for free fermion states \citep{fishman2015}.

### Variational Uniform Matrix Product States and Tree Tensor Networks

In collaboration with colleagues at the University of Ghent and the University of Vienna, I helped to develop a new algorithm for finding ground states of quasi-1D quantum systems directly in the thermodynamic limit, which is faster at finding ground states than the state-of-the-art alternatives. The algorithm is called the variational uniform matrix product state (VUMPS) algorithm \citep{stauber2017}.

In collaboration with colleagues at the CCQ, I worked on extending the VUMPS algorithm to solve for ground states of infinite tree tensor networks states, such as states on the Bethe lattices, in an algorithm we called VUTS \citep{lunts2020}.

### Improved Contraction Methods for Infinite 2D Tensor Networks

In collaboration with colleagues at the University of Ghent and the University of Vienna, I worked on extending the VUMPS algorithm to the problem of contracting infinite 2D tensor networks and showed that in many cases it outperforms the standard method, the corner transfer matrix renormalization group (CTMRG) algorithm. In addition, I worked on a fixed point formulation of CTMRG which we also showed was faster than the original CTMRG algorithm, which we called the fixed point corner method (FPCM) \citep{fishman2017}.

### Easing the Sign Problem with Variational Circuits and Automatic Differentation

With colleagues from CCQ and other institutions, I helped develop a method for decreasing the average sign of a wavefunction by optimizing a quantum circuit ansatz with automatic differentiation \citep{torlai2019}.

## References

* \biblabel{fishman2015}{Fishman et al. (2015)} **Fishman** **White** [Compression of Correlation Matrices and an Efficient Method for Forming Matrix Product States of Fermionic Gaussian States](https://arxiv.org/abs/1504.07701), 2015.
* \biblabel{stauber2017}{Zauner-Stauber et al. (2017)} **Zauner-Stauber** **Vanderstraeten** **Fishman** **Verstraete** **Haegeman** [Variational optimization algorithms for uniform matrix product states](https://arxiv.org/abs/1701.07035), 2017.
* \biblabel{fishman2017}{Fishman et al. (2017)} **Fishman** **Vanderstraeten** **Zauner-Stauber** **Haegeman** **Verstraete** [Faster Methods for Contracting Infinite 2D Tensor Networks](https://arxiv.org/abs/1711.05881), 2017.
* \biblabel{lunts2020}{Lunts et al. (2020)} **Lunts** **George** **Stoudenmire** **Fishman** [The Hubbard model on the Bethe lattice via variational uniform tree states: metal-insulator transition and a Fermi liquid](https://arxiv.org/abs/2010.06543), 2020.
* \biblabel{fishman2020}{Fishman et al. (2020)} **Fishman** **White** **Stoudenmire** [The ITensor Software Library for Tensor Network Calculations](https://arxiv.org/abs/2007.14822), 2020.
* \biblabel{torlai2019}{Torlai et al. (2019)} **Torlai** **Carrasquilla** **Fishman** **Melko** **Fisher** [Wavefunction positivization via automatic differentiation](https://arxiv.org/abs/1906.04654), 2019.
