# Hello, ASP Chef!

## Search for (Stable) Models

Now add the **Search Models** operation, one of those you are going to use more frequently.
In the large text area type the following ASP rules:
```asp
{say("Hello")}.
```
Also increase the __# of models__ to 2.
By now the output should be the following:
```asp
Error: Expecting 2 models, found 1.
§
say("ASP Chef").
§
say("ASP Chef").
say("Hello").
```

ASP recipes are based on a very simple concept:
**Arrays of models are processed by each ingredient in the recipe, according to a parameterized function given by the ingredient itself.**
For each model in input, the **Search Models** operation combines the atoms in the model (mapped to facts or constraints) with a set of ASP rules, and produces one or more models in output.

You may notice that an error is raised because the combination of the first model in input with the additional choice rule actually leads to only one stable model.
The validation on the number of computed models can be disabled by clicking the **RAISE ERROR** button.
The output is now the following:
```asp
say("Hello").
§
say("ASP Chef").
§
say("ASP Chef").
say("Hello").
```
