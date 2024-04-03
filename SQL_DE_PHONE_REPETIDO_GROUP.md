```MYSQL
/*Query phone repetido*/
SELECT
 Phone_value,
        
 Count(Phone_value) AS RepetidoS
FROM
 tb00_natvc_whatsapp_base_optin
GROUP BY
 Phone_Value
```
