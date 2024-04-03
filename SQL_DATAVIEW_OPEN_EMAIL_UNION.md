# Query para selecionar dados que interagiram com os emails em disparos diferentes.
## Foi necessario usar FROM dAS bases para pegar o email de disparo, pois não tem na Data view de _open

```MYSQL
SELECT DISTINCT A.PERSON_ID,
        A.EMAIL_VALUE
FROM [2023_CRM_NCV_DISPAROS_AMPLA_90HIGH_DUPLICADOS] A
WHERE EXISTS (SELECT 1
    FROM _OPEN O
    WHERE O.SUBSCRIBERKEY = A.PERSON_ID
        AND O.JOBID = '386168'
        AND ISUNIQUE = 1)

UNION

SELECT DISTINCT A.PERSON_ID,
        A.EMAIL_VALUE
FROM [2023_CRM_NCV_DISPAROS_AMPLA_90MEDIUM_DUPLICADOS ] A
WHERE EXISTS (SELECT 1
    FROM _OPEN O
    WHERE O.SUBSCRIBERKEY = A.PERSON_ID
        AND O.JOBID = '386169'
        AND ISUNIQUE = 1)
 
UNION 

SELECT DISTINCT A.PERSON_ID,
        A.EMAIL_VALUE
FROM [2023_CRM_NCV_DISPAROS_AMPLA_90LOW_DUPLICADOS] A
WHERE EXISTS (SELECT 1
    FROM _OPEN O
    WHERE O.SUBSCRIBERKEY = A.PERSON_ID
        AND O.JOBID = '386180'
        AND ISUNIQUE = 1)
```