```MySQL
/*  Query retira bounce e reclamação e coloca 55 na frente do telefone 
e pega os engajados dos ultimos 90d*/
SELECT A.person_id,
       email_value,
       canal_recomendador,
       dsc_filial,
       filial,
       Concat('55', phone_value) AS PHONE_VALUE,
       first_name,
       'BR'                      AS LOCALE
FROM   [tb00_20240401_email_bbb24] A
       INNER JOIN _open O
               ON O.subscriberkey = A.person_id
WHERE  CONVERT(CHAR(10), O.eventdate, 120) >=
       CONVERT(CHAR(10), Getdate() - 120, 120)
       AND NOT EXISTS (SELECT Comp.subscriberkey
                       FROM   _complaint Comp
                       WHERE  A.person_id = Comp.subscriberkey
                              AND CONVERT(CHAR(10), Comp.eventdate, 120) >=
                                  CONVERT(CHAR(10), Getdate() - 30, 120))
       /* TIRANDO RECLAMAÇÕES */
       AND NOT EXISTS (SELECT Bo.subscriberkey
                       FROM   _bounce Bo
                       WHERE  A.person_id = bo.subscriberkey
                              AND CONVERT(CHAR(10), bo.eventdate, 120) >=
                                  CONVERT(CHAR(10),
                                  Getdate() - 30, 120)) /* TIRANDO BOUNCE*/
```
