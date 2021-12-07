+++
title = "Projects"
+++

# Projects

\toc

# Coding Projects

## ITensors.jl

I am the lead developer of [ITensors.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl), a full port of the [C++ ITensor library ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensor) to the Julia language. It is a library co-developed with [Miles Stoudenmire ~~~<i class="fas fa-external-link-alt"></i>~~~](http://itensor.org/miles) for easily developing and running high performance tensor network calculations.

~~~<i class="fas fa-newspaper"></i>~~~  __What's New:__ Derivatives of basic tensor network operations using automatic differentiation are now supported. Reverse mode automatic differentiation (AD) primitives are defined using [ChainRules.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaDiff/ChainRules.jl), and derivatives can be computed with AD libraries like [Zygote.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/FluxML/Zygote.jl).

[~~~<i class="fas fa-external-link-alt"></i>~~~ itensor.org](https://itensor.org)

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl)

~~~<i class="fas fa-file-alt"></i>~~~ \cite{fishman2020}

### ITensorGLMakie.jl

[ITensorGLMakie.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGLMakie) is a package I wrote for easily making interactive visualizations of tensor networks written with ITensors.jl, based on [GraphMakie.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaPlots/GraphMakie.jl) and [Makie.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/JuliaPlots/Makie.jl).

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGLMakie)

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

### ITensorGPU.jl

[ITensorGPU.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGPU) is a a GPU backend for ITensors.jl primarily written by [Katie Hyatt ~~~<i class="fas fa-external-link-alt"></i>~~~](https://github.com/kshyatt) while she was a postdoc at the CCQ.

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensors.jl/tree/main/ITensorGPU)

### ITensorNetworkAD.jl

[ITensorNetworkAD.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensorNetworkAD.jl) is an experimental tensor network automatic differentiation (AD) library based on [ITensors.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensors.jl), started by [Linjian Ma ~~~<i class="fas fa-external-link-alt"></i>~~~](https://linjianma.github.io) while he was a summer intern at the CCQ. It makes use of [AutoHOOT ~~~<i class="fab fa-github"></i>~~~](https://github.com/LinjianMa/AutoHOOT), a Python library for symbolic derivatives and simplifications of tensor networks.

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensorNetworkAD.jl)

### Other extensions to ITensors.jl

Many packages are in development that extend the functionality of ITensors.jl, such as packages for performing network level contractions and gradient optimizations of tensor networks, packages for interfacing with quantum chemistry libraries like PySCF, and more. Stay tuned and keep an eye out on my [Github page ~~~<i class="fab fa-github"></i>~~~](https://github.com/mtfishman), the [ITensor Github organization ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor), and the [ITensor website ~~~<i class="fas fa-external-link-alt"></i>~~~](https://itensor.org)!

## PastaQ.jl

[PastaQ.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/GTorlai/PastaQ.jl) is a package I co-develop with [Giacomo Torlai ~~~<i class="fas fa-external-link-alt"></i>~~~](https://github.com/GTorlai) for simulating and analyzing quantum computers, including noisy state and process simulation with customizable noise models, state-of-the-art algorithms for tomography and ongoing work using automatic differentiation to optimize quantum circuits for implementing algorithms like variational quantum eigensolver (VQE) and optimal control.

[~~~<i class="fas fa-external-link-alt"></i>~~~ pastaq.org](https://pastaq.org)

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/GTorlai/PastaQ.jl)

## ITensor (C++)

[ITensor ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/ITensor) is a C++ library for developing and performing tensor network calculations. I was the lead developer of [C++ ITensor Version 3 ~~~<i class="fas fa-external-link-alt"></i>~~~](https://itensor.org/news.html), the latest major release of the library which had many improvements to the interface and performance of block sparse calculations, including the introduction of blocks sparse multithreading with OpenMP.

[~~~<i class="fas fa-external-link-alt"></i>~~~ itensor.org](https://itensor.org)

[~~~<i class="fab fa-github"></i>~~~ Source code](https://github.com/ITensor/ITensor)

## Miscellaneous Julia Packages

### Observers.jl

I co-developed [Observers.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/GTorlai/Observers.jl) with [Giacomo Torlai ~~~<i class="fas fa-external-link-alt"></i>~~~](https://github.com/GTorlai). It is a package for conveniently specifying a set of measurements you want to make inside of an iterative method.

### SerializedElementArrays.jl

[SerializedElementArrays.jl ~~~<i class="fab fa-github"></i>~~~](https://github.com/ITensor/SerializedElementArrays.jl) is a package I wrote that provides a new Julia Array type (a SerializedElementArray) whose elements are saved to disk. This can help in cases where you have collections of large contiguous data (like an Array of very large Arrays) which individually fit in memory but collectively do not. This is used for the write-to-disk feature in ITensors.jl.

## Tensor Network algorithm development

### Free Fermion Tensor Networks

[Steven White ~~~<i class="fas fa-external-link-alt"></i>~~~](https://faculty.sites.uci.edu/dmrg/) and I developed an algorithm for obtaining a compact quantum circuit of local gates for a free fermion state. This leads to a straightforward way to construct tensor network state like matrix product states (MPS), tree tensor networks (TTN), and multi-scale entanglement renormalization ansatz (MERA) for free fermion states.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{fishman2015}

### Variational Uniform Matrix Product States and Tree Tensor Networks

In collaboration with colleagues at the University of Ghent and the University of Vienna, I helped to develop a new algorithm for finding ground states of quasi-1D quantum systems directly in the thermodynamic limit, which is faster at finding ground states than the state-of-the-art alternatives. The algorithm is called the variational uniform matrix product state (VUMPS) algorithm.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{stauber2017}

In collaboration with colleagues at the CCQ, I worked on extending the VUMPS algorithm to solve for ground states of infinite tree tensor networks states, such as states on the Bethe lattices, in an algorithm we called the variational uniform tree state (VUTS) algorithm.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{lunts2020}

### Improved Contraction Methods for Infinite 2D Tensor Networks

In collaboration with colleagues at the University of Ghent and the University of Vienna, I worked on extending the VUMPS algorithm to the problem of contracting infinite 2D tensor networks and showed that in many cases it outperforms the standard method, the corner transfer matrix renormalization group (CTMRG) algorithm. In addition, I worked on a fixed point formulation of CTMRG which we also showed was faster than the original CTMRG algorithm, which we called the fixed point corner method (FPCM).

~~~<i class="fas fa-file-alt"></i>~~~ \cite{fishman2017}

### Easing the Sign Problem with Variational Circuits and Automatic Differentation

With colleagues from CCQ and other institutions, I helped develop a method for decreasing the average sign of a wavefunction by optimizing a quantum circuit ansatz with automatic differentiation. This could have implications for improving the performance of monte carlo algorithms.

~~~<i class="fas fa-file-alt"></i>~~~ \cite{torlai2019}

## References

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{fishman2015}{Fishman et al. (2015)} **Fishman, White** [Compression of Correlation Matrices and an Efficient Method for Forming Matrix Product States of Fermionic Gaussian States](https://arxiv.org/abs/1504.07701), 2015.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{stauber2017}{Zauner-Stauber et al. (2017)} **Zauner-Stauber, Vanderstraeten, Fishman, Verstraete, Haegeman** [Variational optimization algorithms for uniform matrix product states](https://arxiv.org/abs/1701.07035), 2017.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{fishman2017}{Fishman et al. (2017)} **Fishman, Vanderstraeten, Zauner-Stauber, Haegeman, Verstraete** [Faster Methods for Contracting Infinite 2D Tensor Networks](https://arxiv.org/abs/1711.05881), 2017.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{lunts2020}{Lunts et al. (2020)} **Lunts, George, Stoudenmire, Fishman** [The Hubbard model on the Bethe lattice via variational uniform tree states: metal-insulator transition and a Fermi liquid](https://arxiv.org/abs/2010.06543), 2020.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{fishman2020}{Fishman et al. (2020)} **Fishman, White, Stoudenmire** [The ITensor Software Library for Tensor Network Calculations](https://arxiv.org/abs/2007.14822), 2020.

~~~<i class="fas fa-file-alt"></i>~~~ \biblabel{torlai2019}{Torlai et al. (2019)} **Torlai, Carrasquilla, Fishman, Melko, Fisher** [Wavefunction positivization via automatic differentiation](https://arxiv.org/abs/1906.04654), 2019.
