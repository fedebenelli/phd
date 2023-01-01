---
title: "Three phase envelopes of asphaltene reservoir fluid: Difficulties in their tracing and"
geometry: margin=2cm
---

Phase equilibria is of great interest in the oil and gas industry, at either
the upstream and downstream processes. The usual approach in phase equilibria
prediction is based on the utilization of flash calculations, which are
computationally intensive. 

A better way of determining phase equilibria regions is by calculating the
whole phase envelope with efficient mathematical methods like the continuation
method proposed by Michelsen [x] for biphasic systems. 

In the case of reservoir fluids, the compositional complexity can give complex
behaviors, due to the high asymmetry in the system which is originated as a
cause of the presence of simple hydrocarbon mixtures, polar compounds and heavy
compounds like asphaltenes. This complexity can cause the origination of a
third incipient phase. Cismondi proposed a method to trace phase envelopes for
system with three phase boundaries on asphaltenic systems, where an incipient
phase could be either a vapor or a liquid [x]. This approach has two important
considerations that must be taken into account: 

- Provide a good initialization to start tracing the boundary line.
- Effectively detect critical points and intelligently readapt the algorithm to
  take this into account.

Developing effective ways to satisfy this two considerations is crucial to
avoid potential incomplete diagrams that could lead to incorrect
interpretations.

Starting from already known cases where some of this conditions aren't fully
satisfied, which results in incomplete phase diagrams that won't fully
represent the studied system and could lead to false assumptions. We explore in
this work possible solutions to this two problems, begining from an analysis on
why these cases diverge and later on how these problems can be battled. We
tackle this two scenarios separatedly, but that doesn't mean that both can't
happen at the same time in the same system.

All the implementations in this work have been structured into a Modern Fortran
Library, available for public use.
