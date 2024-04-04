```MySQL

/*Seleciona Block Bounce para usar como critério de exclusão no warmup*/

SELECT subscriberkey,
       bouncecategory,
       bouncetype,
       eventdate
FROM   _bounce
WHERE  bouncecategory = 'Block bounce' 
```
