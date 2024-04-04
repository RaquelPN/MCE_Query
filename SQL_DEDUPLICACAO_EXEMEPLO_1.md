```MySQL

/*Exemplo Query Deduplicação no caso de ter 2 primarykey na DE
Essa juntava Id_Lead + ID_plano */

SELECT c.id_lead AS ID,
       c.locale,
       c.numero_telefone
FROM   (SELECT id_lead,
               'BR'                         AS Locale,
               numero_telefone,
               Row_number()
                 OVER (
                   partition BY id_lead
                   ORDER BY id_plano DESC ) AS flag
        FROM
[tb_historico_jornada_yeah_mkt_no_oportunidade-em-andamento-aguardando-pagamento]
) AS c
WHERE  flag = 1 

```
