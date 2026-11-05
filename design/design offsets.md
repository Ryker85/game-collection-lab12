# The eight offsets

Each square shows the offset `(dr, dc)` from the middle cell, where `dr` is the
change in row and `dc` is the change in column. Row numbers grow downward and
column numbers grow to the right.

```
+---------+---------+---------+
| (-1,-1) | (-1, 0) | (-1,+1) |
+---------+---------+---------+
| ( 0,-1) |  XXXXX  | ( 0,+1) |
|         |  (0,0)  |         |
+---------+---------+---------+
| (+1,-1) | (+1, 0) | (+1,+1) |
+---------+---------+---------+
```

The middle square `(0, 0)` is the cell itself, so it is **crossed out**: it is
not a neighbor. The other eight squares are the neighbors.

In `count\_neighbors` these are the two nested loops `dr in -1..=1` and
`dc in -1..=1`, with `(0, 0)` skipped.



