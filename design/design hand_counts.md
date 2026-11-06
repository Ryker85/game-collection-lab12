# Verify by hand

Grid is 10 rows x 20 columns, indexes count from 0. A neighbor beyond the edge
counts as dead. Only the cells that are not 0 are worked out below; every cell
not mentioned has no live cell within one step, so its count is 0.

## Case 1: vertical line of three in the middle

Live cells: (4,10), (5,10), (6,10).

|Cell|Live neighbors|Working|
|-|-|-|
|(3,9), (3,10), (3,11)|1|only (4,10) is adjacent|
|(4,9), (4,11)|2|(4,10) and (5,10)|
|(4,10)|1|(5,10); the cell itself is not counted|
|(5,9), (5,11)|3|(4,10), (5,10), (6,10)|
|(5,10)|2|(4,10) and (6,10)|
|(6,9), (6,11)|2|(5,10) and (6,10)|
|(6,10)|1|(5,10); the cell itself is not counted|
|(7,9), (7,10), (7,11)|1|only (6,10) is adjacent|

Expected `print\_neighbor\_counts` output (columns 9, 10, 11 of rows 3 to 7):

```
row 3:  0 0 0 0 0 0 0 0 0 1 1 1 0 0 0 0 0 0 0 0
row 4:  0 0 0 0 0 0 0 0 0 2 1 2 0 0 0 0 0 0 0 0
row 5:  0 0 0 0 0 0 0 0 0 3 2 3 0 0 0 0 0 0 0 0
row 6:  0 0 0 0 0 0 0 0 0 2 1 2 0 0 0 0 0 0 0 0
row 7:  0 0 0 0 0 0 0 0 0 1 1 1 0 0 0 0 0 0 0 0
```

(printed without spaces by the program; rows 0-2, 8 and 9 are all zeros)

## Case 2: vertical line of three down the left edge, from the top-left corner

Live cells: (0,0), (1,0), (2,0).

|Cell|Live neighbors|Working|
|-|-|-|
|(0,0)|1|(1,0); nothing above or to the left (off the grid = dead)|
|(1,0)|2|(0,0) and (2,0)|
|(2,0)|1|(1,0)|
|(3,0)|1|(2,0)|
|(0,1)|2|(0,0) and (1,0)|
|(1,1)|3|(0,0), (1,0), (2,0)|
|(2,1)|2|(1,0) and (2,0)|
|(3,1)|1|(2,0)|

Expected output (first columns):

```
row 0:  1 2 0 0 ...
row 1:  2 3 0 0 ...
row 2:  1 2 0 0 ...
row 3:  1 1 0 0 ...
row 4+: 0 0 0 0 ...
```

## Did the program agree?

Option 6 in `play` draws both lines on one grid (they are 10 columns apart, so
they do not touch and the counts do not affect each other). Compare the
digits printed under "Neighbor counts:" with the tables above.

* Middle line: **agreed**
* Corner line: **agreed**

