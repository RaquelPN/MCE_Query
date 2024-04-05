```Mysql
SELECT TOP 100
    Jobid,
    EventDate
FROM _Sent
    WHERE EventDate  <= GETDATE() AND EventDate >= '2024-03-05'
    ORDER BY EventDate asc
```
```Mysql
/*Forma mais segura para a data vir correta*/

SELECT TOP 100
    Jobid,
    CONVERT (VARCHAR ,EVENTDATE, 103) as EventDate
FROM _Sent
    WHERE EventDate  <= GETDATE() AND EventDate >= '2024-03-05'
    ORDER BY CONVERT (VARCHAR ,EVENTDATE, 103) asc
```
