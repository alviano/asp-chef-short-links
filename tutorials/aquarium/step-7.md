# Output Format

The output is expected to be a CSV as follows:

> `S` lines of `S` chars each, where `.` denotes a free cell, and `*` denotes a cell with water.
Let's replace the mocked output with a real function computing the output.

Add a **Search Models** with the following content:
```asp
__cell__(I,J,"*") :- water(I,J).
__cell__(I,J,".") :- group(I,J,_), not water(I,J).
```

After that, add a **Generate CSV** ingredient and remove the separator.
Finally, add a **Select Predicates** ingredient, select only `__base64__` and activate the **DECODE** flag in the **Output Panel**.
You should see the following output:
```
****..
**.***
.*..**
***.**
*....*
***.**
```