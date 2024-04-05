```Mysql
SELECT TOP 100
    Jobid,
    EventDate
FROM _Sent
    WHERE EventDate  <= GETDATE() AND EventDate >= '2024-03-05'
    ORDER BY EventDate asc
```
```Mysql
/*Forma mais recomendada oba praticas VARCHAR
 que faz a data virar caracter (para sequencia numeros)*/

SELECT TOP 100
    Jobid,
    CONVERT (VARCHAR ,EVENTDATE, 103) as EventDate
FROM _Sent
    WHERE EventDate  <= GETDATE() AND EventDate >= '2024-03-05'
    ORDER BY CONVERT (VARCHAR ,EVENTDATE, 103) asc
```
```Mysql
/*Forma que faz a data virar data datetime (para sequencia de numeros)*/

SELECT TOP 100
    Jobid,
    CONVERT (datetime ,EVENTDATE, 103) as EventDate
FROM _Sent
    WHERE EventDate  <= GETDATE() AND EventDate >= '2024-03-05'
    ORDER BY CONVERT (datetime ,EVENTDATE, 103) asc
```
