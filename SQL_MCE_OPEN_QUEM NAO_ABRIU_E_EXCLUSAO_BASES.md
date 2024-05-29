


Select
a.PERSON_ID, 
a.EMAIL_VALUE
From 	tb00_20240511_nav_dia_das_maes_Optin a
Inner Join  ent._Subscribers as  s ON s.Subscriberkey = a.PERSON_ID
inner join _open as o ON o.Subscriberkey = s.Subscriberkey
    Where o.Jobid not in ('435881','433777','436686' )
        and not exists (select b.PERSON_ID  
                  From [tb00_20240509_nav_mn_ofertas_abril_maio_ofertas_disparo23_05_disparo] b 
                  Where s.Subscriberkey = b.PERSON_ID)
        and not exists (select c.PERSON_ID  
                  From [20240528_EMAIL_NHS_MAIODEOFERTAS_ACVMHS_V3_OPTIN] c 
                  Where s.Subscriberkey = c.PERSON_ID)

UNION

Select
a.PERSON_ID, 
a.EMAIL_VALUE
From [202405010_EMAIL_NHS_MAIODEOFERTAS_ACVMHS_V1] a
Inner Join  ent._Subscribers as  s ON s.Subscriberkey = a.PERSON_ID
inner join _open as o ON o.Subscriberkey = s.Subscriberkey
 Where o.Jobid not in ('435881','433777','436686' )
        and not exists (select b.PERSON_ID  
                  From [tb00_20240509_nav_mn_ofertas_abril_maio_ofertas_disparo23_05_disparo] b 
                  Where s.Subscriberkey = b.PERSON_ID)
        and not exists (select c.PERSON_ID  
                  From [20240528_EMAIL_NHS_MAIODEOFERTAS_ACVMHS_V3_OPTIN] c 
                  Where s.Subscriberkey = c.PERSON_ID)

UNION

Select
a.PERSON_ID, 
a.EMAIL_VALUE
From [tb00_202405010_nav_cc_maio_ofertas_disparo_16_05_Optin] a
Inner Join  ent._Subscribers as  s ON s.Subscriberkey = a.PERSON_ID
inner join _open as o ON o.Subscriberkey = s.Subscriberkey
 Where o.Jobid not in ('435881','433777','436686' )
        and not exists (select b.PERSON_ID  
                  From [tb00_20240509_nav_mn_ofertas_abril_maio_ofertas_disparo23_05_disparo] b 
                  Where s.Subscriberkey = b.PERSON_ID)
        and not exists (select c.PERSON_ID  
                  From [20240528_EMAIL_NHS_MAIODEOFERTAS_ACVMHS_V3_OPTIN] c 
                  Where s.Subscriberkey = c.PERSON_ID)
validação

SELECT
a.PERSON_ID,
a.EMAIL_VALUE
FROM optin_tb00_20240509_nav_mn_ofertas_maio_modulen_disparo10_05_2 a
inner join 	[20240510_EMAIL_NHS_MAIODEOFERTAS_MN_V1] as b ON a.PERSON_ID = b.PERSON_ID
inner join 	[20240516_EMAIL_NHS_MAIODEOFERTAS_MN_V2_DISPARO] as c ON a.PERSON_ID = c.PERSON_ID
