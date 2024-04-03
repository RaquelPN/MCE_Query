```MySQL

/*PRimeira forma puxando da tabela maior*/

SELECT
a.SubscriberKey
FROM 
_SMSMessageTracking a
WHERE a.Subscriberkey IN (SELECT Person_id
    FROM [20240402_SMS_NATVC_NO_BEES] b
    WHERE a.SubscriberKey = b.Person_id )
AND a.Delivered = 1
AND a.Name = '20240402_SMS_NATVC_NO_BEES'

/*Segunda forma puxando da tabela menor*/

Select
a.person_id,
FROM [20240402_SMS_NATVC_NO_BEES] a
inner
JOIN _SMSMessageTracking b
    ON a.person_id = b.SubscriberKey
WHERE b.Name = '20240402_SMS_NATVC_NO_BEES'
AND b.Delivered = 1
```
