# Teaching order and prerequisites

- Start with no assumed programming knowledge. Use the numbered notebooks in week order.
- Introduce a new operation, demonstrate it on a small known input, then let students change one input.
- Prefer separate statements and named results. A shorter solution is not automatically easier to teach.
- Loops are first taught in the Week 2 control-flow lesson. Function definitions are first taught in Week 3.
- Week 4 uses lists and dictionaries for API records. Pandas first appears in Week 5.
- Instructor setup and offline fixture plumbing live outside the student examples.
- Examples containing a deliberate error keep the failing line commented. Students can test it separately; running the teacher notebook does not depend on try/except before that concept is introduced.

| Order | First introduce | Build on |
| --- | --- | --- |
| Week 1, Syntax | print, text, names, order of execution, comments | No prior knowledge |
| Week 1, Variables | assignment, types, conversion, one result at a time | Syntax |
| Week 1, Data types/operators | text operations, arithmetic, comparisons, Boolean values | Variables |
| Week 2, Data structures | lists, tuples, sets, dictionaries, copying, unpacking | Basic values and indexing |
| Week 2, Control flow | if/elif/else, indentation, while, for, range, break/continue | Collections and comparisons |
| Week 3, Functions | define/call, parameters, return, then defaults and scope | Control flow and collections |
| Week 3, NumPy | literal arrays, shape/dtype, then reshape/join/filter | Collections, loops, functions |
| Week 4, APIs | one request, one response, JSON records, then error handling | Lists/dictionaries/loops |
| Week 4, Databases | connection, cursor, SQL, parameters, cleanup | Strings, tuples, loops |
| Week 5, pandas | Series/DataFrames, selection, filtering, summaries, then joins/reshape | Records and NumPy |
| Week 7, Visualization | one chart, then subplot axes, group comparisons, analysis | pandas and array operations |
| Week 7, Food project | combine known tools; add sentiment scoring explicitly | APIs, pandas, visualization |
| Additional practice, Spotify | independent project; optional statistical extensions | Complete the earlier lessons first |

