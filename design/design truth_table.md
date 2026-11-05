# Truth table for `next\_state`

One cell has 2 states (alive / dead) and 0 to 8 live neighbors (9 values),
so the table needs 2 x 9 = **18 rows**.

Rules used (from the lab page): a live cell with 2 or 3 live neighbors stays
alive; a dead cell with exactly 3 live neighbors becomes alive; every other
cell is dead in the next generation.

|#|Alive now?|Live neighbors|Alive next generation?|Why|
|-|-|-|-|-|
|1|dead|0|dead|needs exactly 3 to be born|
|2|dead|1|dead|needs exactly 3 to be born|
|3|dead|2|dead|needs exactly 3 to be born|
|4|dead|3|**alive**|born: exactly 3 neighbors|
|5|dead|4|dead|needs exactly 3 to be born|
|6|dead|5|dead|needs exactly 3 to be born|
|7|dead|6|dead|needs exactly 3 to be born|
|8|dead|7|dead|needs exactly 3 to be born|
|9|dead|8|dead|needs exactly 3 to be born|
|10|alive|0|dead|underpopulation|
|11|alive|1|dead|underpopulation|
|12|alive|2|**alive**|survives|
|13|alive|3|**alive**|survives|
|14|alive|4|dead|overpopulation|
|15|alive|5|dead|overpopulation|
|16|alive|6|dead|overpopulation|
|17|alive|7|dead|overpopulation|
|18|alive|8|dead|overpopulation|

Only 3 of the 18 rows give a live cell next generation: rows 4, 12 and 13.
A live cell survives with **2 or 3** neighbors (rows 12 and 13); a dead cell
is born with **exactly 3** neighbors (row 4).

