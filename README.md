# mermaid

## 2024

### soccer players spanning significant periods

```mermaid
gantt
dateFormat  YYYY
title Players

section A section
Matthews      : 1932,1965
Shilton    : 1966,1997
O'Leary  : 1975,1995
Maradona    : 1976,1997
vierchwood    : 1976,2000
Matthaus  : 1978,2000
zubizaretta    : 1979,1998
Bergomi :  1979,1999
Laudrup    : 1981,1998
Sanchis    : 1983,2001
Maldini    : 1984,2009
De Boer    : 1988,2008
giggs    : 1990,2014
shevchecko    : 1993,2012
totti    : 1993,2017
buffon    : 1995,2023
Torres    : 2001,2019
```
### Budget
```mermaid
---
config:
  sankey:
    showValues: false
---
sankey-beta

Agricultural 'waste',Bio-conversion,124.729
Bio-conversion,Liquid,0.597
Bio-conversion,Losses,26.862
Bio-conversion,Solid,280.322
Bio-conversion,Gas,81.144
Biofuel imports,Liquid,35
Biomass imports,Solid,35
Coal imports,Coal,11.606
Coal reserves,Coal,63.965
Coal,Solid,75.571
District heating,Industry,10.639
District heating,Heating and cooling - commercial,22.505
District heating,Heating and cooling - homes,46.184
Electricity grid,Over generation / exports,104.453
Electricity grid,Heating and cooling - homes,113.726
Electricity grid,H2 conversion,27.14
Electricity grid,Industry,342.165
Electricity grid,Road transport,37.797
Electricity grid,Agriculture,4.412
Electricity grid,Heating and cooling - commercial,40.858
Electricity grid,Losses,56.691
Electricity grid,Rail transport,7.863
Electricity grid,Lighting & appliances - commercial,90.008
Electricity grid,Lighting & appliances - homes,93.494
Gas imports,Ngas,40.719
Gas reserves,Ngas,82.233
Gas,Heating and cooling - commercial,0.129
Gas,Losses,1.401
Gas,Thermal generation,151.891
Gas,Agriculture,2.096
Gas,Industry,48.58
Geothermal,Electricity grid,7.013
H2 conversion,H2,20.897
H2 conversion,Losses,6.242
H2,Road transport,20.897
Hydro,Electricity grid,6.995
Liquid,Industry,121.066
Liquid,International shipping,128.69
Liquid,Road transport,135.835
Liquid,Domestic aviation,14.458
Liquid,International aviation,206.267
Liquid,Agriculture,3.64
Liquid,National navigation,33.218
Liquid,Rail transport,4.413
Marine algae,Bio-conversion,4.375
Ngas,Gas,122.952
Nuclear,Thermal generation,839.978
Oil imports,Oil,504.287
Oil reserves,Oil,107.703
Oil,Liquid,611.99
Other waste,Solid,56.587
Other waste,Bio-conversion,77.81
Pumped heat,Heating and cooling - homes,193.026
Pumped heat,Heating and cooling - commercial,70.672
Solar PV,Electricity grid,59.901
Solar Thermal,Heating and cooling - homes,19.263
Solar,Solar Thermal,19.263
Solar,Solar PV,59.901
Solid,Agriculture,0.882
Solid,Thermal generation,400.12
Solid,Industry,46.477
Thermal generation,Electricity grid,525.531
Thermal generation,Losses,787.129
Thermal generation,District heating,79.329
Tidal,Electricity grid,9.452
UK land based bioenergy,Bio-conversion,182.01
Wave,Electricity grid,19.013
Wind,Electricity grid,289.366
```

## 2023
### Atletico players

```mermaid
gantt
dateFormat  YYYY
title Atletico Players

section A section
aparicio    : 1938,1952
escudero : 1945,1958
collar    : 1952,1969
rivilla    : 1954,1968
calleja    : 1958,1972
Adelardo               :done,  1959,1976
Luis Aragones            :done,    1964,1974
Garate:done,1966,1977
tomas    : 1984,1996
aguilera : 1988 , 2005
antonio lopez: 2001, 2004
antonio lopez: 2004, 2012
mejias: 1981,1993
koke    : 2013,2024
oblak    : 2014,2024
Joao Felix               :         2019, 2022
```

### Stadiums
```mermaid
gantt
dateFormat  YYYY
title Stadiums

section A section
San Mames    : 1938,1952
Vicente Calderon : 1945,1958
Sarria: 1998,2000
Roker Park: 1998,2000
Ayresome Park: 1998,2000
Stadium of Light: 1998,2000
Pride Park: 1998,2000
Madjetski Stadium: 1998,2000
Reebok Stadium: 1998,2000
Highbury: 1998,2000
Maine Road: 1998,2000
Anoeta: 1998,2000
White Hart Lane: 1998,2000
Park de Princes: 1998,2000
Tartiere: 1998,2000
Lluís Sitjar: 1998,2000
Filbert Street: 1998,2000
```
### Sequence diagram

```mermaid

sequenceDiagram
    "AbstractLogger.java" ->> "AbstractMessageFactory.java" : newMessage()
    "AbstractMessageFactory.java" ->> "SimpleMessage.java" : SimpleMessage()
    "SimpleMessage.java" ->> "AbstractMessageFactory.java" : "return Message"
    "AbstractMessageFactory.java" ->> "AbstractLogger.java" : "return Message"
    "AbstractLogger.java" ->> "Logger.java" : log()
```

Sequence diagrams are better than data flow diagrams for typical OOP code (with mutable state) because the data flow is chained rather than linear, and the column alignment by class allows you to see the common class easily

Options for sequence diagrams:
* Qsde
* Textdiagram
* Mermaid
* Plantuml
* Textart.io (ASCII.sequence: https://textart.io/sequence, https://github.com/weidagang/text-diagram)
   * I've made a command line version here: ~/src.git/javascript/sequence_diagram/text-diagram.js

```
+---------------------+         +-------------------------+                 +---------------+ +-------------+    +-----------------------------------------+  +-------------------------+   +-----------------------+ +-----------------------------------+ +---------------------+   +---------------------------+
| AbstractLogger_java |         | AbstractMessageFactory  |                 | SimpleMessage | | Logger_java |    | AwaitCompletionReliabilityStrategy_java |  | AsyncLoggerConfig_java  |   | AppenderControl_java  | | AbstractOutputStreamAppender_java | | AbstractLayout_java |   | OutputStreamManager_java  |
+---------------------+         +-------------------------+                 +---------------+ +-------------+    +-----------------------------------------+  +-------------------------+   +-----------------------+ +-----------------------------------+ +---------------------+   +---------------------------+
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           | newMessage(string)              |                                      |                |                                |                                    |                            |                               |                              |                            |
           |-------------------------------->|                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 | return SimpleMessage(string)         |                |                                |                                    |                            |                               |                              |                            |
           |                                 |------------------------------------->|                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                        SimpleMessage |                |                                |                                    |                            |                               |                              |                            |
           |                                 |<-------------------------------------|                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                  return Message |                                      |                |                                |                                    |                            |                               |                              |                            |
           |<--------------------------------|                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           | log(Message)                    |                                      |                |                                |                                    |                            |                               |                              |                            |
           |---------------------------------------------------------------------------------------->|                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                | log(data)                      |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |------------------------------->|                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                | log(event : LogEvent)              |                            |                               |                              |                            |
           |                                 |                                      |                |                                |----------------------------------->|                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    | callAppender()             |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |--------------------------->|                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            | append()                      |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |------------------------------>|                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               | encode()                     |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |----------------------------->|                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |
           |                                 |                                      |                |                                |                                    |                            |                               |                              | writeBytes()               |
           |                                 |                                      |                |                                |                                    |                            |                               |                              |--------------------------->|
           |                                 |                                      |                |                                |                                    |                            |                               |                              |                            |


```




### TODO: Wimbledon victories (gantt)


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
