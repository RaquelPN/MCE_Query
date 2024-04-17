```MySQL

SELECT 
person_id,
        
EMAIL_VALUE,
        
Pergunta_01,
        
Pergunta_02,
        
 
    CASE
    WHEN CHARINDEX('|', Pergunta_03) > 0 THEN
    LEFT(Pergunta_03, CHARINDEX('|', Pergunta_03) - 1)
    ELSE Pergunta_03
    END AS Pergunta_03_1,
 
    CASE 

    WHEN CHARINDEX('|', Pergunta_03, CHARINDEX('|', Pergunta_03) + 1) > 0 
 THEN
    SUBSTRING(Pergunta_03, CHARINDEX('|', Pergunta_03) + 1, CHARINDEX('|', Pergunta_03, CHARINDEX('|', Pergunta_03) + 1) - CHARINDEX('|', Pergunta_03) - 1) 

    ELSE NULL 

    END AS Pergunta_03_2,
 
    CASE 

    WHEN CHARINDEX('|', Pergunta_03, CHARINDEX('|', Pergunta_03) + 1) > 0 
 THEN
    RIGHT(Pergunta_03, LEN(Pergunta_03) - CHARINDEX('|', Pergunta_03, CHARINDEX('|', Pergunta_03) + 1)) 

    ELSE NULL 

    END AS Pergunta_03_3,
Pergunta_04,
Pergunta_05,
Pergunta_06,

    CASE
    WHEN CHARINDEX('|', Pergunta_07) > 0 THEN
    LEFT(Pergunta_07, CHARINDEX('|', Pergunta_07) - 1)
    ELSE Pergunta_07
    END AS Pergunta_07_sozinho,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) - CHARINDEX('|', Pergunta_07) - 1)
    ELSE NULL
    END AS Pergunta_07_companheiro,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) - CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) - 1)
    ELSE NULL
    END AS Pergunta_07_pais,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) - CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) - 1)
    ELSE NULL
    END AS Pergunta_07_filhos,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) - CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) - 1)
    ELSE NULL
    END AS Pergunta_07_avos,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) - CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) - 1)
    ELSE NULL
    END AS Pergunta_07_outros_familiares,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) - CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) - 1)
    ELSE NULL
    END AS Pergunta_07_nao_familiares,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) - CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) - 1)
    ELSE NULL
    END AS Pergunta_07_outros,

    CASE
    WHEN CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) > 0 THEN
    SUBSTRING(Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) + 1) - CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07, CHARINDEX('|', Pergunta_07) + 1) + 1) + 1) - 1)
    ELSE NULL
    END AS Pergunta_07_irmaos,
Pergunta_08,
Pergunta_09,
Pergunta_10
FROM Tb_Respostas_Formulario_Pesquisa_Antigos_Contatos_concat


```
