# Visualization

If I were in your shoes, I would try to have a nice graphical visualization as soon as possible.
And I would have it with ASP Chef!

## The Graph Operation

The easiest way to obtain a graphical representation is via the **Graph** operation.
You can add it now, but as you can check in the pop-up docs a graph is expected to be encoded by predicate `__graph__` (or anything specified in the ingredient).

How are we going to materialize such a predicate?
With ASP Chef, obviously!
Let's add a **Search Models** operation before the **Graph** ingredient, and type in the following content:
```asp
__graph__(node(cell(I,J)),
  fx(J * 10), fy(I * 10)
) :- size(R,C), I = 1..R, J = 1..C.

__graph__(node(poi(I,J)),
  fx(J * 10), fy(I * 10),
  label(V),
  color(white),
  shape(circle)
) :- poi(I,J,V).

__graph__(defaults,
  node_shape(square),
  node_radius(5)
).
```

Well done!
You may have noticed that the output is still containing `size/2` and `poi/3`, while predicate `__graph__` is not present anymore.
This is because the new instances of predicate `__graph__` were eventually **consumed** by the **Graph** ingredient.
If you want to preserve them, just click the **ECHO** button.
(I assume you will not echo them.)