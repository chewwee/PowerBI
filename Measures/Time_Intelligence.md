### Create a Date Table 

```DAX
date = 
VAR mindate = YEAR(MIN(financials[Date]))
RETURN
ADDCOLUMNS(
    FILTER(
        CALENDARAUTO(),
        [Date] >= mindate
    ),
    "Year",YEAR([Date]),
    "Quarter Num",QUARTER([Date]),
    "Quarter", "Q"&QUARTER([date]),
    "Month Num",MONTH([Date]),
    "Month",FORMAT([Date],"mmm"),
    "Week Num",WEEKNUM([Date]),
    "Day",day([Date]),
    "Weekday",FORMAT([Date],"ddd"),
    "Weekday Num", WEEKDAY([Date])
)
```
![Screenshot 2023-09-18 202716](https://github.com/chewwee/PowerBI/assets/90857289/8ae228f2-b6af-4b67-867f-e747779476f8)
