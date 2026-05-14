# ASP Chef notes

This file captures general working notes about ASP Chef and the patterns used in this session.

## Core ideas

1. ASP Chef is a pipeline: each ingredient transforms the current model(s) and passes the result to the next one.
2. A common workflow is: parse input -> derive ASP relations -> visualize/debug -> optimize/solve -> visualize the solution.
3. The fastest way to understand the environment is to use `Search Operations`, `Get Operation Docs`, and `Get Recipe`.

## Important operations

### Parse CSV

- `Parse CSV` is a raw parser.
- It turns delimited text into facts such as `csv_cell(Row,Col,Value)`.
- It should usually be followed by ASP rules that map those generic cells into domain predicates.

### Search Models

- `Search Models` is the main place to derive domain relations.
- Use it to define predicates like `size/2`, `poi/3`, `covered/2`, `inside/2`, `wall/2`, and similar.
- Control what survives to later ingredients with `#show`.

### Optimize

- `Optimize` is for optimization via weak constraints.
- Use `Set Optimization Strategy` immediately before it when you need to tune clingo.
- Lexicographic optimization is modeled with weak-constraint levels.

## Good modeling habits

1. Put computation in ASP ingredients such as `Search Models` and `Optimize`.
2. Keep `Encode` focused on producing rendering/configuration data.
3. If rendering needs a distinction, derive separate predicates in ASP first instead of trying to express logic inside a template.
4. Show only the predicates that later ingredients need.

## Encode and visualization notes

### Encode

- `Encode` with Mustache is not JavaScript.
- Inline expressions such as ternaries are not valid there.
- If you need conditional rendering, derive separate ASP predicates and expand them separately.

### Fabric.js

- `Fabric.js` consumes a Base64-encoded JSON configuration, commonly produced by `Encode` into `__json__`.
- Rendering is layer-based: objects generated later visually sit on top of earlier ones.
- It helps to set `originX: 'center'` and `originY: 'center'` explicitly to avoid alignment mistakes.

## Practical visualization pattern

For grid problems, a robust drawing order is:

1. Base cells
2. Coverage / intermediate overlays
3. Solution-region overlays
4. POI cells
5. POI labels
6. Walls or other final markers

## Problem-modeling lesson from this session

- The exact predicate design matters more than the drawing.
- For example, deciding whether a wall is an edge or a cell changes both the optimization model and the visualization.
- Once that semantic choice is fixed in ASP, the renderer becomes straightforward.
