```MYSQL
/*Query warmup IP exemplo 1*/


SELECT email,
       NAME,
       cpf
FROM   (SELECT email,
               NAME,
               cpf,
               Row_number()
                 OVER(
                   partition BY CASE WHEN email LIKE '%@live.%' OR email LIKE
                 '%@msn.%'
                 OR
                 email LIKE '%@hotmail.%' OR email LIKE '%@outlook.%' OR email
                 LIKE
                 '%@windowslive.%' THEN 'hotmail.com' WHEN email LIKE
                 '%@yahoo.%' OR
                 email LIKE
                 '%@ymail.%' THEN 'yahoo.com' WHEN email LIKE '%@gmail.%' OR
                 email LIKE
                 '%@googlemail.%' THEN 'gmail.com' ELSE 'outros' END
                   ORDER BY email) indice
        FROM   tb_warmup_engajados_150d a
        WHERE  NOT EXISTS (SELECT ''
                           FROM   tb_hard_block_bounce s WITH(nolock)
                           WHERE  s.subscriberkey = a.email)
               AND NOT EXISTS (SELECT ''
                               FROM   tb_optout_backup s WITH(nolock)
                               WHERE  s.subscriberkey = a.email)) AS tb
WHERE  tb.indice <= CASE
                      WHEN email LIKE '%@live.%'
                            OR email LIKE '%@msn.%'
                            OR email LIKE '%@hotmail.%'
                            OR email LIKE '%@windowslive.%'
                            OR email LIKE '%@outlook.%' THEN 38185
                      WHEN email LIKE '%@yahoo.%'
                            OR email LIKE '%@ymail.%' THEN 4580
                      WHEN email LIKE '%@gmail.%'
                            OR email LIKE '%@googlemail.%' THEN 512733
                      ELSE 2745
                    END
GROUP  BY tb.email,
          tb.NAME,
          tb.cpf 
```
```MYSQL
/*Query warmup IP exemplo 2*/

SELECT email,
       NAME
FROM   (SELECT email,
               NAME,
               Row_number()
                 OVER(
                   partition BY CASE WHEN email LIKE '%@live.%' OR email LIKE
                 '%@msn.%'
                 OR
                 email LIKE '%@hotmail.%' OR email LIKE '%@outlook.%' OR email
                 LIKE
                 '%@windowslive.%' THEN 'hotmail.com' WHEN email LIKE
                 '%@yahoo.%' OR
                 email LIKE
                 '%@ymail.%' THEN 'yahoo.com' WHEN email LIKE '%@gmail.%' OR
                 email LIKE
                 '%@googlemail.%' THEN 'gmail.com' ELSE 'outros' END
                   ORDER BY email) indice
        FROM   tb_warmup_engajados_150d a) AS tb
WHERE  tb.indice <= CASE
                      WHEN email LIKE '%@live.%'
                            OR email LIKE '%@msn.%'
                            OR email LIKE '%@hotmail.%'
                            OR email LIKE '%@windowslive.%'
                            OR email LIKE '%@outlook.%' THEN 100
                      WHEN email LIKE '%@yahoo.%'
                            OR email LIKE '%@ymail.%' THEN 100
                      WHEN email LIKE '%@gmail.%'
                            OR email LIKE '%@googlemail.%' THEN 1500
                      ELSE 100
                    END
GROUP  BY tb.email,
          tb.NAME
```

```MySQL
/*Query warmup IP exemplo 3*/

SELECT email
FROM   (
                SELECT   email,
                         Row_number() OVER(partition BY
                         CASE
                                  WHEN email LIKE '%live.com'
                                  OR       email LIKE '%live.com.br'
                                  OR       email LIKE '%msn.com'
                                  OR       email LIKE '%msn.com.br'
                                  OR       email LIKE '%hotmail.com'
                                  OR       email LIKE '%hotmail.com.br'
                                  OR       email LIKE '%outlook.com'
                                  OR       email LIKE '%outlook.com.br' THEN 'hotmail.com'
                                  WHEN email LIKE '%yahoo.com'
                                  OR       email LIKE '%yahoo.com.br' THEN 'yahoo.com'
                                  ELSE Substring(email, Charindex('@',email)+1,9999)
                         END ORDER BY email) indice
                FROM     base_total_emcasa a
                WHERE    NOT EXISTS
                         (
                                SELECT ''
                                FROM   tb_myraliscasa_blockbounce s WITH(nolock)
                                WHERE  s.subscriberkey = a.email)
                AND      NOT EXISTS
                         (
                                SELECT ''
                                FROM   tb_warmup_myraliscasa_150322 s WITH(nolock)
                                WHERE  s.email = a.email)
                AND      NOT EXISTS
                         (
                                SELECT ''
                                FROM   tb_warmup_myraliscasa_160322 s WITH(nolock)
                                WHERE  s.email = a.email)
                AND      NOT EXISTS
                         (
                                SELECT ''
                                FROM   tb_warmup_myraliscasa_170322 s WITH(nolock)
                                WHERE  s.email = a.email)
                AND      NOT EXISTS
                         (
                                SELECT ''
                                FROM   tb_warmup_myraliscasa_180322 s WITH(nolock)
                                WHERE  s.email = a.email)
                AND      NOT EXISTS
                         (
                                SELECT ''
                                FROM   tb_warmup_myraliscasa_190322 s WITH(nolock)
                                WHERE  s.email = a.email)
                AND      NOT EXISTS
                         (
                                SELECT ''
                                FROM   tb_warmup_myraliscasa_200322 s WITH(nolock)
                                WHERE  s.email = a.email) ) AS tb
WHERE  tb.indice <= when email LIKE '%live.com'
OR     email LIKE '%live.com.br'
OR     email LIKE '%msn.com'
OR     email LIKE '%msn.com.br'
OR     email LIKE '%hotmail.com'
OR     email LIKE '%hotmail.com.br'
OR     email LIKE '%windowslive.com'
OR     email LIKE '%windowslive.com.br'
OR     email LIKE '%outlook.com'
OR     email LIKE '%outlook.com.br' THEN
518
WHEN email LIKE '%yahoo.com'
  OR
  email LIKE '%yahoo.com.br' THEN
  100
WHEN email LIKE '%gmail.com'
  OR
  email LIKE '%gmail.com.br' THEN
  1904
  ELSE 50
END
GROUP BY tb.email
```

```MySQL
/*Query warmup IP exemplo 4*/

SELECT email
FROM   (SELECT email,
               Row_number()
                 OVER(
                   partition BY CASE WHEN email LIKE '%live.com' OR email LIKE
                 '%live.com.br'
                 OR email LIKE '%msn.com' OR email LIKE '%msn.com.br' OR email
                 LIKE
                 '%hotmail.com' OR email LIKE '%hotmail.com.br' OR email LIKE
                 '%outlook.com' OR
                 email LIKE '%outlook.com.br' THEN 'hotmail.com' WHEN email LIKE
                 '%yahoo.com'
                 OR email LIKE '%yahoo.com.br' THEN 'yahoo.com' ELSE Substring(
                 email,
                 Charindex
                 ('@', email)+1, 9999) END
                   ORDER BY email) indice
        FROM   base_total_emcasa a
        WHERE  NOT EXISTS (SELECT ''
                           FROM   tb_myraliscasa_blockbounce s WITH(nolock)
                           WHERE  s.subscriberkey = a.email)
               AND NOT EXISTS (SELECT ''
                               FROM   tb_warmup_myraliscasa_280322 s WITH(nolock
                                      )
                               WHERE  s.email = a.email)
               AND NOT EXISTS (SELECT ''
                               FROM   tb_warmup_myraliscasa_290322 s WITH(nolock
                                      )
                               WHERE  s.email = a.email)) AS tb
WHERE  tb.indice <= CASE
                      WHEN email LIKE '%live.com'
                            OR email LIKE '%live.com.br'
                            OR email LIKE '%msn.com'
                            OR email LIKE '%msn.com.br'
                            OR email LIKE '%hotmail.com'
                            OR email LIKE '%hotmail.com.br'
                            OR email LIKE '%windowslive.com'
                            OR email LIKE '%windowslive.com.br'
                            OR email LIKE '%outlook.com'
                            OR email LIKE '%outlook.com.br' THEN 2164
                      WHEN email LIKE '%yahoo.com'
                            OR email LIKE '%yahoo.com.br' THEN 0
                      WHEN email LIKE '%gmail.com'
                            OR email LIKE '%gmail.com.br' THEN 5005
                      ELSE 100
                    END
GROUP  BY tb.email
```
