```Mysql
SELECT TOP 100
    Jobid,
    EventDate
FROM _Sent
    WHERE EventDate  <= GETDATE() AND EventDate >= '2024-03-05'
    ORDER BY EventDate asc
```
