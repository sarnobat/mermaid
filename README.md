# mermaid

### Atletico players
```mermaid
gantt
dateFormat  YYYY
title Atletico Players

section A section
Luis Aragones            :done,    1964,1974
Adelardo               :done,  1959,1976
Garate:done,1966,1977
Joao Felix               :         2019, 222
```

### Nutrition info
Find low carb foods.

```mermaid
pie
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```

### Sequence diagram

Sequence diagrams are better than data flow diagrams for typical OOP code (with mutable state) because the data flow is chained rather than linear, and the column alignment by class allows you to see the common class easily

Options for sequence diagrams:
* Qsde
* Textdiagram
* Mermaid
* Plantuml
* Textart.io (ASCII.sequence: https://textart.io/sequence)


```mermaid
sequenceDiagram
    "AbstractLogger.java_info()" ->>John: Hello John, how are you?
    John-->>Alice: Great!
    Alice-)John: See you later!
```
