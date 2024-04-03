```MySQL
/*Query abertura recente*/
SELECT DISTINCT a.person_id, o.eventdate AS Data_abertura_recente, a.email_value, o.jobid
               
FROM   [_open] AS o
inner JOIN tb00_natvc_send_click_open AS a
              ON o.subscriberkey = a.person_id
              where Isunique = '1' and o.eventdate >= getdate()-1
```
