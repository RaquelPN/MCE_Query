```MySQL

SELECT 
person_id,
Pergunta_01,
Pergunta_02,
  CASE 
        WHEN CHARINDEX('|', pergunta_03) > 0 THEN SUBSTRING(pergunta_03, 1, CHARINDEX('|', pergunta_03) - 1) 
        ELSE pergunta_03 
    END AS Pergunta_03_1,
    CASE 
        WHEN CHARINDEX('|', pergunta_03) > 0 THEN SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) - CHARINDEX('|', pergunta_03) - 1) 
        ELSE NULL 
    END AS Pergunta_03_2,
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) > 0 THEN SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1)) 
        ELSE NULL 
    END AS Pergunta_03_3,
Pergunta_04,
Pergunta_05,
Pergunta_06,
CASE 
        WHEN CHARINDEX('|', PERGUNTA_07) > 0 THEN SUBSTRING(PERGUNTA_07, 1, CHARINDEX('|', PERGUNTA_07) - 1) 
        ELSE PERGUNTA_07 
    END AS Pergunta_07_sozinho,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) - CHARINDEX('|', PERGUNTA_07) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_companheiro,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_pais,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_filhos,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_avos,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_outros_familiares,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_nao_familiares,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_outros,
    
    CASE 
        WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1) + 1) + 1) + 1, LEN(PERGUNTA_07) - CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07, CHARINDEX('|', PERGUNTA_07) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS Pergunta_07_irmaos,
Pergunta_08,
Pergunta_09,
Pergunta_10,
EMAIL_VALUE
FROM
Tb_Respostas_Formulario_Pesquisa_Antigos_Contatos_concat


```


```MySQL

SELECT
    CASE 
        WHEN CHARINDEX('|', pergunta_03) > 0 THEN SUBSTRING(pergunta_03, 1, CHARINDEX('|', pergunta_03) - 1) 
        ELSE pergunta_03 
    END AS resposta1,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) - CHARINDEX('|', pergunta_03) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03)) 
            END
        ELSE 
            NULL 
    END AS resposta2,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1)) 
            END
        ELSE 
            NULL 
    END AS resposta3,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS resposta4,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS resposta5,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS resposta6,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS resposta7,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS resposta8,
    
    CASE 
        WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
            CASE 
                WHEN CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) > 0 THEN 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) + 1, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) - 1) 
                ELSE 
                    SUBSTRING(pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1) + 1) + 1) + 1, LEN(pergunta_03) - CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03, CHARINDEX('|', pergunta_03) + 1) + 1) + 1)) 
            END
        ELSE 
            NULL 
    END AS resposta9
    
FROM
    tb_Roberta;
apps-fileview.texmex_20240404.01_p0
ander.txt
Página 9 de 10

```
