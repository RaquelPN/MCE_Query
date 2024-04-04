```MySQL
/*Seleciona Block Bounce para usar como critério de exclusão no warmup*/

SELECT subscriberkey,
       bouncecategory,
       bouncetype,
       eventdate
FROM   _bounce
WHERE  bouncecategory = 'Block bounce' 
```
```MySQL
/*Seleciona  os Bounces para usar como critério de exclusão no warmup*/

SELECT SubscriberKey,
       BounceCategory,
       BounceType,
       EventDate
FROM   _bounce
WHERE BounceCategory in ('Hard bounce','Soft bounce', 'Block bounce')
```
