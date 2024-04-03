```MYSQL
SELECT DISTINCT a.email_value,
                a.zipcode,
                a.numero_endereco,
                a.bairro_endereco,
                a.region,
                a.first_name,
                a.last_name,
                a.sex,
                a.phone_value,
                a.birthdate,
                a.idade,
                a.city,
                a.person_id,
                a.marital_status,
                a.optin_nhs_cadu,
                a.optin_geral_cadu
FROM   [tb00_Tabela_1] a
       INNER JOIN _open o ON a.person_id = o.subscriberkey
WHERE  ( o.eventdate >= Getdate() - 90 )
       AND NOT EXISTS (SELECT 1 FROM tb00_Tabela_2 b  WHERE  a.person_id = b.person_id)
         AND NOT EXISTS (SELECT 1 FROM tb00_Tabela_3 c WHERE  a.person_id = c.person_id)
           AND NOT EXISTS (SELECT 1 FROM tb00_Tabela_4 d WHERE a.person_id = d.person_id) 
           ```
