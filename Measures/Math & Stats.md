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
