```MySQL
/*Query contagem provedor exemplo 1*/
select top 99999999 provedore,count(provedore) as total
from (
		select 
		case when 
		c.EMAIL_VALUE like '%live.com.br' or c.EMAIL_VALUE like '%msn.com.br' 
		or c.EMAIL_VALUE like '%hotmail.com.br' or c.EMAIL_VALUE like '%outlook.com.br' 
		or c.EMAIL_VALUE like '%live.com' or c.EMAIL_VALUE like '%msn.com' 
		or c.EMAIL_VALUE like '%hotmail.com' or c.EMAIL_VALUE like '%outlook.com' then 'hotmail.com'
		when EMAIL_VALUE like '%yahoo.com' or EMAIL_VALUE like '%yahoo.com.br' then 'yahoo.com'		
		else substring(c.EMAIL_VALUE, charindex('@',c.EMAIL_VALUE)+1,9999) 
		end provedore, count(distinct c.EMAIL_VALUE) as total
		from tb_engajados c
		group by EMAIL_VALUE
) t  
group by provedore
order by 2 desc
```

```MySQL
/* WARMUP Contagem de provedor exemplo2*/

select top 99999999 provedore,count(provedore) as total
from (
		select 
		case when 
		c.email like '%live.com.br' or c.email like '%msn.com.br' 
		or c.email like '%hotmail.com.br' or c.email like '%outlook.com.br' 
		or c.email like '%live.com' or c.email like '%msn.com' 
		or c.email like '%hotmail.com' or c.email like '%outlook.com' then 'hotmail.com'
		when email like '%yahoo.com' or email like '%yahoo.com.br' then 'yahoo.com'		
		else substring(c.email, charindex('@',c.email)+1,9999) 
		end provedore, count(distinct c.email) as total
		from Base_total_EmCasa c
		group by email
) t  
group by provedore
order by 2 desc
```
