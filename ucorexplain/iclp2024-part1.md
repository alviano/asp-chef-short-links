UCOREXPLAIN vs XASP2
====================

Explanation graphs produced for two instances of Sudoku.

Each cell value reports the time and memory required to compute an explanation.
The number of links and the number of assumptions are also reported, and a link to the graph is included.

The number of links is actually an overestimate:

* UCOREXPLAIN uses self-loops to label inferences by unit-constraints;
* XASP2 uses links to `#false` and `#true` (which are not shown in the navigator).

The assumptions used by XASP2 are not necessarily part of the induced explanation graph.
