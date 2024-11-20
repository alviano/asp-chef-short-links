# Visualization

Let's shape a nice graphical visualization already now.

## The Graph Operation

Let's add a **Search Models** operation followed by a **Graph** ingredient, and type in the following content:
```asp
color(1,red).
color(2,blue).
color(3,green).
color(4,orange).
color(5,purple).
color(6,gray).

__graph__(node((I,J)),
  fx(40 + J*40), fy(40 + I*40),
  color(Color)
) :- group(I,J,G), color(G,Color).

__graph__(node((I,J)),
  label(w)
) :- water(I,J).

__graph__(node((row_clue, Row)),
  label(Clue),
  fx(40 + Row*40), fy(40),
  color(transparent)
) :- row_clue(Row, Clue).

__graph__(node((col_clue, Col)),
  label(Clue),
  fx(40), fy(40 + Col*40),
  color(transparent)
) :- col_clue(Col, Clue).

__graph__(defaults,
  node_shape(square),
  node_radius(19)
).
```

Well done!
