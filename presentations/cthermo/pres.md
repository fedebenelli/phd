---
theme: Luebeck
---

# "Hands-on" section

## What we propose you to do? 

Make a Flash PT algorithm 

## What will we use?

You can use whichever programming language you feel comfortable with.

We can assist you if you use either Python with our library `PyForFluids`
or Fortran with our other library `feos`


# PyForFluids (Python-Fortran-Fluids)

`PyForFluids` is a Python library that calculates Fluid thermodynamic properties
using Fortran routines in the background to assure calculations robustness
and speed.

\vspace{1em}

\small
```python
fluid = pff.Fluid(
    model=model,
    composition=composition,
    temperature=temperature,
    pressure=pressure
)

fluid["lnfug"]

>>> [0.15, 0.2, 0.5]
```
\normalsize

# feos (Fortran Equations of State)

`feos` is a Modern Fortran library that implement equations of state
calculations. It's partially the Fortran routines of `PyForFluids`.

\tiny
```fortran
   compounds(1) = PR("methane", tc=191.15_wp, pc=46.41_wp, w=0.0115_wp)
   compounds(2) = PR("ethane",  tc=305.3_wp,  pc=49.0_wp,  w=0.099_wp)
   compounds(3) = PR("propane", tc=369.9_wp,  pc=42.5_wp,  w=0.1521_wp)

   kij = reshape(&
       [0.0, 0.4, 0.3, &
        0.4, 0.0, 0.1, &
        0.3, 0.1, 0.0],&
        [n, n] &
       )
   lij = 0*kij

   mixing_rule = ClassicVdW(kij=kij, lij=lij)

   compounds%moles = 1.0_wp/n
   mixture%components = compounds
   mixture%mixing_rule = mixing_rule

   t = 250
   v = 10_wp
   ar =  mixture%residual_helmholtz(v, t)
```
\vspace{1em}
> Right now it doesn't go beyond calculating the Helmholtz energy
> and it's derivatives.
\normalsize

