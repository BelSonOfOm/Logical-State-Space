# The Logical State Space

Charbel Dargham, M1 Quantum Information, Sorbonne Université (autumn 2026).

The Logical State Space is a construction meant to play, for algorithms, the role a connectome plays for a brain: a structure from which behaviour can be read. The behaviour that matters most here is whether the quantum circuit running an algorithm can be simulated efficiently by a classical computer, that is, whether it can be dequantized. The object of the construction is the algorithm that solves a problem, not the problem itself. It has two axes: a temporal axis that follows the algorithm step by step, and a relational axis made of layers, where layer 0 is how the inputs are related before the algorithm does anything, layer 1 how the algorithm connects them, and higher layers hold relations of higher order. On every layer and at every time it attaches a hypergraph (which variables are related), a sheaf (what the related variables are) and a dynamics (how their states change); the toric ideal of the hypergraph then turns the structure into algebraic invariants. The work states definitions and choices and computes them on examples; it proves no theorem yet.

## The documents

`LSS_first_description.pdf` (28 October 2026) is the first description of the construction. Every definition is introduced together with three running examples, breadth-first search on small graphs, quantum teleportation and the BB84 key-distribution protocol, with the reason for each choice and what has been computed on the examples. Sources carry a grade according to whether they were opened and checked, and the invariants were computed exactly with Macaulay2 or numerically at the stated precision.

`LSS_constructions.pdf` constructs the first two layers on the three examples: the variables, their domains and the schedule; layer 0; layer 1 step by step; the sheaf on the variables; the dynamics, following the state; and how the structure evolves through time. On breadth-first search layer 0 carries the whole structure of the input graph and layer 1 uses part of it; on teleportation layer 1 and the sheaf show the one strong relation of layer 0 being moved from one pair of qubits to another; on BB84 layer 0 is empty, and an intercept–resend eavesdropper appears in layer 1 as a pair of operations on the same vertices in opposite directions, and in the sheaf as an error rate of one quarter.

`LSS_temporal_gluing.pdf` glues the temporal axis of a layer. It sets directed labelled hypergraphs up as C-sets, glues the snapshots of a run along their shared variables into an occurrence hypergraph O, identifies occurrences into a relation hypergraph R, and reads both through their toric ideals, with a proposition relating the ideal of O to that of R. On the three examples, the relations among the relations of layer 1 are few: none for breadth-first search, exactly one for teleportation, involving every kind of operation of the protocol, and for BB84 only relations coming from the eavesdropper's operations.

Each `.tex` source sits next to its PDF; `figs_constructions/` and `figs_gluing/` hold the figures of the second and third documents. The sources compile with pdflatex from this folder.

## Applications

The first application to data is layer zero of a dataset of learning problems, in [BelSonOfOm/Experiments_for_trainability_and_simul](https://github.com/BelSonOfOm/Experiments_for_trainability_and_simul), under `LAYER0/`.
