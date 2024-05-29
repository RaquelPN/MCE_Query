Select
s.Subscriberkey as PERSON_ID, 
s.EmailAddress as EMAIL_VALUE
From ent._Subscribers as  s 
inner join _open as o ON o.Subscriberkey = s.Subscriberkey
    Where o.Jobid not in ('435881','433777' , '436686' )
        and not exists (select b.PERSON_ID  
                  From [tb00_20240509_nav_mn_ofertas_maio_modulen_disparo27_05_optin] b 
                  Where s.Subscriberkey = b.PERSON_ID)
        and not exists (select c.PERSON_ID  
                  From [tb00_202405010_nav_cc_maio_ofertas_disparo_23_05_disparo] c 
                  Where s.Subscriberkey = c.PERSON_ID)
        and not exists (select d.PERSON_ID  
                  From [tb00_20240509_nav_mn_ofertas_abril_maio_ofertas_disparo23_05_disparo] d 
                  Where s.Subscriberkey = d.PERSON_ID)
