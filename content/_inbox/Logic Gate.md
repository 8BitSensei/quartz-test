2023-10-30
Tags: #electronics #logic 
##### AND Gate
True only when both inputs are true
Logically A /\\ B

| A   | B   | Output |
| --- | --- | ------ |
| 0   | 0   | 0      |
| 0   | 1   | 0      |
| 1   | 0   | 0      |
| 1   | 1   | 1      |

##### NOT Gate (inverter)
Outputs the opposite value of the input
Logically ¬A

| A   | Output |
| --- | --- |
| 0   | 1      |
| 1   | 0      |

##### NAND (NOT-AND) Gate
false only if all its inputs are false.
Logically ¬(A /\\ B)

| A   | B   | Output |
| --- | --- | ------ |
| 0   | 0   | 1      |
| 0   | 1   | 1      |
| 1   | 0   | 1      |
| 1   | 1   | 0      |

##### NOR Gate
True only if all are false
Logically ¬(A V B)

|A|B|Output|
|---|---|---|
|0|0|1|
|0|1|0|
|1|0|0|
|1|1|0|

##### OR Gate
False only when all else are false (opposite of AND)
Logically A V B

|A|B|Output|
|---|---|---|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|1|