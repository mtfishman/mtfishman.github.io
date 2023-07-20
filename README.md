# [mtfishman.github.io](https://mtfishman.github.io)
Source code for [mtfishman.github.io](https://mtfishman.github.io), the personal website of Matt Fishman ([@mtfishman](https://github.com/mtfishman)), Research Scientist and Software Engineer at the Flatiron Institute Center for Computational Quantum Physics (CCQ).

The site is built with [Franklin.jl](https://github.com/tlienart/Franklin.jl), based on the [basic Franklin template](https://tlienart.github.io/FranklinTemplates.jl).

To build and view the website locally, first [install Julia](https://julialang.org/downloads).
Then clone the repository locally, and in the base directory run:
```julia
$ julia

julia> using Franklin

julia> serve()
  Activating project at `~/software/mtfishman.github.io`
→ Initial full pass...
→ Starting the server...
✓ LiveServer listening on http://localhost:8000/ ...
  (use CTRL+C to shut down)
```
Then open your browser and navigate to the URL [localhost:8000](http://localhost:8000/).
