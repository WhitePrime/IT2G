# Создание сертификата OpenVPN для офиса

Инструкция по выдаче подключения по OpenVPN

[https://172.17.21.1:10000](https://172.17.21.1:10000/)

adm-hd

d71c331df198

Выбираем «Службы» - OpenVPN + CA

Для выпуска нового сертификата

Certification Authority List

![C:\8a8a1a9bb7a95afe64f1bdbef18bb79a](../.gitbook/assets/0%20%283%29.png)

Выводим список ключей:

![C:\ab070cf75601b722914cd67d17ed69d1](../.gitbook/assets/1%20%287%29.png)

Опускаемся ниже и вводим имя согласно доменной учетной записи:

![C:\19584f034a57ba722e4303a2ad349ff6](../.gitbook/assets/2%20%282%29.png)

Создаем нового клиента VPN нажав

VPN List

![C:\2116f41b193dbd35bcc594c8f2e8b536](../.gitbook/assets/3%20%281%29.png)

Открываем

Client List

![C:\692035f10e9b9d012393aad3b430f07b](../.gitbook/assets/4%20%284%29.png)

Опускаемся ниже и нажимаем

New VPN Client

![C:\5d1a04a4393df4bf28144f5a4ff770c5](../.gitbook/assets/5%20%282%29.png)

1. Выбираем и выпадающего списка имя
2. Вводим IP address сервера
3. Fast LZO – NO
4. заполняем поле «ccd file content»
5. Жмем
6. Сохранить

IP server

185.118.64.212

ccd file content

push "route 172.17.20.0 255.255.255.0"

push "route 172.17.21.0 255.255.255.0"

push "dhcp-option DNS 172.17.21.3"

push "dhcp-option DNS 172.17.21.9"

![C:\35d6b626f248055d8265ef7fb2938072](../.gitbook/assets/6%20%281%29.png)

![C:\07315bf1c30c823e8f8254ac42a9b50e](../.gitbook/assets/7%20%281%29.png)

Далее выбираем из списка выпущенный сертификат и нажимаем

Export

![C:\58fcbbb9b88ce6daccbeed8611e153b1](../.gitbook/assets/8.png)

Удаляем из архива файл dh2048.per

![C:\123d85279b8a0cafcba205ac1c3f7430](../.gitbook/assets/9%20%283%29.png)

Открываем файлы с расширением .conf и .ovpn через блокнот или Notepad++,  удаляем строчку «dh2048.percert»

![C:\88833fba0b9586863f0c914fe0f0b32a](../.gitbook/assets/10%20%281%29.png)

После строки Remote вставляем 

tls-cipher "DEFAULT:@SECLEVEL=0"

![C:\17ae8d04d7585e884c100696821a5413](../.gitbook/assets/11.png)

Архив с ссылкой на ПО OpenVPN отправляем заявителю на доменную почту.

Ссылка для загрузки OpenVPN: [https://openvpn.net/index.php/open-source/downloads.html](https://openvpn.net/index.php/open-source/downloads.html)

