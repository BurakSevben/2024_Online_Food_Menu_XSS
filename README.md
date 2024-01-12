# 2024_Online_Food_Menu_XSS

+ **Exploit Title:** 2024_Online_Food_Menu_XSS
+ **Date:** 2024-11-01
+ **Exploit Author:** Burak Sevben
+ **Vendor Homepage:** https://www.sourcecodester.com/php/17096/online-food-menu-using-php-and-mysql-source-code.html
+ **Software Link:** https://www.sourcecodester.com/download-code?nid=17096&title=Online+Food+Menu+Using+PHP+and+MySQL+with+Source+Code
+ **Version:** 1.0
+ **Tested on:** Windows 11 Home  + PHP 8.2.12, Apache 2.4.58
+ **Payload 1 :** `<video/src=x onerror=alert(document.domain)>`
+ **Payload 2 :** `<video/src=x onerror=alert(document.cookie)>`
+ **CVE:** Reported, waiting for CVE number

## Description:
The 'Menu Name' and 'Description' fields in the Update Menu section of `localhost/food-menu/admin.php` are vulnerable to cross-site scripting.   An attacker could exploit this issue to run arbitrary script code in the browser of an unsuspecting user in the context of the affected site. This could allow the attacker to steal cookie-based authentication credentials and launch other attacks.

## Proof of Concept:
+ Go to `localhost/food-menu/admin.php`  You will see the previously saved data (menus).
+ To update a random data (one of the menus), select 'Update Menu'  A window will appear. 
+ Enter the following payload in the 'Menu Name' field: `<video/src=x onerror=alert(document.domain)>`
+ XSS will be triggered as soon as you press the Save Changes button.
+ Select a random data (one of the menus) again, select the 'Update Menu' option and enter the following payload in the 'Description' section of the window that appears: `<video/src=x onerror=alert(document.cookie)>`
+ XSS will be triggered as soon as you press the  Save Changes button.


# Menu Name
![Ekran görüntüsü 2024-01-12 021626](https://github.com/BurakSevben/2024_Online_Food_Menu_XSS/assets/117217689/16b744c9-74b6-4957-92cb-0ce8c74b0b4b)
![Ekran görüntüsü 2024-01-12 021645](https://github.com/BurakSevben/2024_Online_Food_Menu_XSS/assets/117217689/1884a231-4f04-4e16-a5df-8193c9955d6a)

# Description
![Ekran görüntüsü 2024-01-12 021737](https://github.com/BurakSevben/2024_Online_Food_Menu_XSS/assets/117217689/6beb7bed-60bb-4db2-b3da-a2bc120faa4c)
![Ekran görüntüsü 2024-01-12 021751](https://github.com/BurakSevben/2024_Online_Food_Menu_XSS/assets/117217689/9cf60f60-242e-45fb-ad08-8a395a3072df)






