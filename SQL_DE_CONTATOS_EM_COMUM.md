```MYSQL
/* Query que compara 2 bases para saber contatos em comum*/
SELECT a.Person_id
FROM [20240403_EMAIL_NATVC_SMART_DAY] a
WHERE a.Person_id IN (
SELECT b.Person_id 

    FROM [20240403_EMAIL_NATVC_MOÇA_340G] b
    WHERE b.person_id = a.person_id
    ``` 
