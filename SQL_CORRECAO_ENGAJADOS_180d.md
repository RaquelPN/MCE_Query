```MySQL
/* Query retira bounce e reclamação e coloca 55 na frente do telefone 
e pega os engajados dos ultimos 180d*/  

SELECT distinct A.PERSON_ID, A.canal_recomendador, A.EMAIL_VALUE, A.dsc_filial, A.filial, A.FIRST_NAME, O.EVENTDATE
FROM tb00_20231122_email_z076_consolidado_teste A

inner join _Open O on O.SubscriberKey = A.person_id

WHERE CONVERT(CHAR(10), O.eventdate, 120) <= CONVERT(CHAR(10), GETDATE() - 91,120) 
AND CONVERT(CHAR(10), O.eventdate, 120) >= CONVERT(CHAR(10), GETDATE() - 180,120)

AND NOT EXISTS (SELECT Comp.subscriberkey FROM _Complaint Comp 
                WHERE A.PERSON_ID = Comp.subscriberkey
                and  CONVERT(CHAR(10), Comp.eventdate, 120) >= CONVERT(CHAR(10), GETDATE() - 30,120))  /* TIRANDO RECLAMAÇÕES */

AND NOT EXISTS (select Bo.subscriberkey from _Bounce Bo
                where A.PERSON_ID = bo.subscriberkey
                and   CONVERT(CHAR(10), bo.eventdate, 120) >= CONVERT(CHAR(10), GETDATE() - 30,120)) /* TIRANDO BOUNCE*/
```
