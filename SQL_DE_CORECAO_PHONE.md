```MySQL
/*Query correção de telefone */
SELECT A.person_id,
       email_value,
       canal_recomendador,
       dsc_filial,
       filial,
       first_name,
       Concat('55', phone_value) AS PHONE_VALUE,
       'BR'                      AS LOCALE
FROM   tb00_20240402_sms_natvc_no_bees A
WHERE  ( phone_value NOT LIKE( '550000%' )
         AND phone_value NOT LIKE( '559999%' )
         AND phone_value NOT LIKE( '551111%' )
         AND phone_value NOT LIKE( '552222%' )
         AND phone_value NOT LIKE( '55' ) )
       AND NOT EXISTS (SELECT 1
                       FROM   _undeliverablesms s
                       WHERE  s.mobilenumber = Concat('55', phone_value)
                              AND s.undeliverable = 1) 
```
