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
