### RANKX
```
Rank = 
RANKX(
   ALLSELECTED(Prod[Product]),
    [Total Gross Sales],
    ,DESC,
    Dense
)
```

```
RankInScope = 
IF(
    ISINSCOPE(Prod[Product]),
    RANKX(
        ALLSELECTED(Prod[Product]),
        [Total Gross Sales],
        ,DESC,
        Dense
    )
)
```

![Screenshot 2023-09-18 225502](https://github.com/chewwee/PowerBI/assets/90857289/cfdb11ef-384e-4ede-9d8a-391712f522fb)


## Running Total 
### Running Total based on date 
```
Sales RT = 
CALCULATE(
   [Total Gross Sales],
   WINDOW(1,ABS,0,REL,
      SUMMARIZE(ALLSELECTED('date'),'date'[Year],'date'[Month],'date'[Month Num]),
      ORDERBY('date'[Year],ASC,'date'[Month Num],ASC),,
      PARTITIONBY('date'[Year])
   )
)
```
```
Sales RT using MAX = 
CALCULATE(
   [Total Gross Sales],
   FILTER(
      ALLSELECTED('date'),
      'date'[date]<=MAX('date'[date'])
   )
)
```
### Running Total Without Date 
```
Prod Sales RT =
CALCULATE(
   [Total Gross Sales],
   WINDOW(1,ABS,0,REL,   -- 1, ABS starts at first row and 0 is current row 
      SUMMARIZE(ALLSELECTED('Prod'),'Prod'[Product]),
      ORDERBY([Total Gross Sales],DESC)
   )
)
```

