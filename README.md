 # mermaid

## 2024
### gitgraph / railroad
https://github.com/sarnobat/atleticomadrid?tab=readme-ov-file#atleticomadrid

### Budget monthly
```mermaid
---
config:
  sankey:
    showValues: true
---
sankey-beta
airbnb,expenses,1900
rental car,expenses,1100
88 property shortfall,expenses,1000
food,expenses,800
1614 property shortfall,expenses,600
storage+insurance,expenses,210
phone,expenses medium,140
youtube TV,expenses medium,84
netflix,expenses small,20
pwtorch,expenses small,10
applecare,expenses small,15
dashpass,expenses small,10
```
### soccer players spanning significant periods

```mermaid
---
displayMode: compact
---
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


## 2023
### Atletico players

```mermaid
---
displayMode: compact
---
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
see also: https://docs.google.com/spreadsheets/d/1wopT5qG15EK1-_W8MO2E5Qeu--ashat0A70WFishQ7I/edit?gid=0#gid=0
```mermaid

---
displayMode: compact
---
gantt
dateFormat  YYYY
title Stadiums

San Mames    : 1913,2013
Vicente Calderon : 1966,2017
Sarria	:	1923	,	1997
Roker Park 	:	1898	,	1997
Ayresome Park 	:	1903	,	1997
Lluís Sitjar 	:	1945	,	1999
Tartiere 	:	1932	,	2000
Filbert Street 	:	1891	,	2002
Maine Road 	:	1923	,	2003
Highbury 	:	1913	,	2006
White Hart Lane 	:	1899	,	2017
```

### Musicians
see also:
* https://docs.google.com/spreadsheets/d/1a8LbwMELrVSXFf-VJ54fop96Cmk_pPUq9ezvaqk-41g/edit?gid=0#gid=0
* https://docs.google.com/spreadsheets/d/1K2K2Is2F2mY2l5gQZ9RBPOK0IRQWak8SNxzKVGvxv1E/edit?gid=1210820633#gid=1210820633
* 
```mermaid

---
displayMode: compact
---
gantt
dateFormat  YYYY
title Musicians

Mozart    : 1900,1901

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
* adia

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
