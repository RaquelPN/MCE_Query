```MySQL
/*query warmup whatsapp Exemplo 1*/
SELECT NAME,
       cpf,
       phone,
       locale
FROM   (SELECT NAME,
               cpf,
               phone,
               locale,
               Row_number()
                 OVER(
                   partition BY locale
                   ORDER BY phone) AS indice
        FROM   tb_warmup_engajados_whatsapp
        WHERE  phone NOT IN ( '0', '55', '' )
               AND phone NOT IN (SELECT phone
                                 FROM   tb_whatsapp_2508)) tb
WHERE  tb.indice <= 100000
```

```MySQL
/*query warmup whatsapp Exemplo 2*/
SELECT primeironome,
       contactkey,
       email,
       phone,
       locale,
       num
FROM   (SELECT primeironome,
               contactkey,
               email,
               phone,
               locale,
               num,
               Row_number()
                 OVER(
                   partition BY locale
                   ORDER BY phone) AS indice
        FROM   tb_base_warmup_whatsapp_loyalty
        WHERE  phone NOT IN ( '0', '55', '' )
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_1411)) tb
WHERE  tb.indice <= 500
```

```MySQL
/*query warmup whatsapp Exemplo 3*/
SELECT primeironome,
       contactkey,
       phone,
       locale
FROM   (SELECT primeironome,
               contactkey,
               phone,
               locale,
               Row_number()
                 OVER(
                   partition BY locale
                   ORDER BY phone) AS indice
        FROM   tb_base_warmup_whatsapp
        WHERE  phone NOT IN ( '0', '55', '' )
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_1411)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_1511)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_1611)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_1711)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_1811)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_1911)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2111)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2211)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2311)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2411)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2511)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2611)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2811)
               AND phone NOT IN (SELECT phone
                                 FROM   tb_warmup_whatsapp_2911)) tb
WHERE  tb.indice <= 1000
```
