```MySQL
/* Query retira bounce e reclamação e coloca 55 na frente do telefone 
e pega os engajados dos ultimos 120d*/    
SELECT A.PERSON_ID,
EMAIL_VALUE,
canal_recomendador,
dsc_filial,
filial,
concat('55', PHONE_VALUE) as PHONE_VALUE,
FIRST_NAME,
'BR' as LOCALE
FROM [tb00_20240401_email_bbb24] A

inner join _Open O on O.SubscriberKey = A.person_id

WHERE CONVERT(CHAR(10), O.eventdate, 120) >= CONVERT(CHAR(10), GETDATE() - 120,120)

AND NOT EXISTS (SELECT Comp.subscriberkey FROM _Complaint Comp 
                WHERE A.PERSON_ID = Comp.subscriberkey
                and  CONVERT(CHAR(10), Comp.eventdate, 120) >= CONVERT(CHAR(10), GETDATE() - 30,120))  /* TIRANDO RECLAMAÇÕES */

AND NOT EXISTS (select Bo.subscriberkey from _Bounce Bo
                where A.PERSON_ID = bo.subscriberkey
                and   CONVERT(CHAR(10), bo.eventdate, 120) >= CONVERT(CHAR(10), GETDATE() - 30,120)) /* TIRANDO BOUNCE*/
``` 
