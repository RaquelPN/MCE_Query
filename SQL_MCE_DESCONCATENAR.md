---MySQL


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

///
