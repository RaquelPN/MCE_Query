```MySQL
/*Query contagem envios whatsapp mes*/
Select top 100000000000000000 month(EventDateUTC) as Mes, year(EventDateUTC) as Ano, count(CHANNELID) as Total
from Tb_Whatsapp_Tracking_90d where status ='sent' 


/*

and ActivityName not in(
'Jornada_OptOut_Whatsapp',
'Jornada_OptOut_Whatsapp_Parar',
'Jornada_OptOut_Whatsapp_Receber',
'Jornada_Atendimento_Whatsapp_Template0',
'Jornada_Template_Atendimento_Key1',
'Jornada_Atendimento_Whatsapp_Key2',
'Jornada_Atendimento_Whatsapp_Key3',
'Jornada_Campanha_Warmup_Whatsapp')

*/

and TRACKINGTYPE = 'SEND' and status ='sent'

and  MONTH(GETDATE()) = MONTH(EventDateUTC )
group by month(EventDateUTC), year(EventDateUTC)
order by month(EventDateUTC)desc, year(EventDateUTC)
```
