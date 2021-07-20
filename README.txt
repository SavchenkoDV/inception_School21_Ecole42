

<img width="1901" alt="Visual_Subject" src="https://github.com/SavchenkoDV/inception_School21_Ecole42/blob/master/example%231.png">


Реализация VirtualBox - Ubuntu 20.04, Containers - debian:buster:
1. Создаем виртуалуальную машину Ubuntu (https://losst.ru/kak-polzovatsya-virtualbox#2_%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_%D0%B2%D0%B8%D1%80%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9_%D0%BC%D0%B0%D1%88%D0%B8%D0%BD%D1%8B)
2. Устанавливаем Docker (https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-ru).
3. Устанавливаем Docker-Compose (https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-ru)
4. Устанавливаем VIM, MAKE, GIT и другик программы, плагины необходимые для работы.
5. Меняем в Ubuntu хосты (/etc/hosts -> localhost на ****.42.fr).
6. Создаем Makefile:
	6.1. Задаем общие настройки Makefile - для удобства сборки и пересборки контейнеров:
		6.1.1. Запуск контейнеров.
		6.1.2. Отключение.
		6.1.3. Удаление и очистка всего.
7. Создаем файл docker-compose.yml (https://dker.ru/docs/docker-compose/compose-file-reference):
	7.1. Создаем network. 
	7.2. Создаем volumes - (https://docs.docker.com/storage/volumes/) + (https://github.com/compose-spec/compose-spec/blob/master/spec.md#volumes-top-level-element)
	7.3. Создаем команды на сборку контейнеров - services. Не забываем подключить network и volume (https://dker.ru/docs/docker-compose/compose-file-reference).
8. NGINX - dockerfile, nginx, config, openssl:
	8.1. Устновливем nginx и openssl.
	8.2. Подписываем сертификат openssl.
	8.3. Изменияем конфиг nginx (etc/nginx/sites-enabled/defaul). Ссылка для общего понимания (https://serveradmin.ru/ustanovka-i-nastrojka-nginx/). В документации все написанно, прийдеться покопаться (https://nginx.org/ru/docs/):
		8.3.1. Синтаксис конфига (https://nginx.org/ru/docs/beginners_guide.html)
		8.3.2. Ищем инфу в интернете, как добавить в конфиг: ssl_portocol TLSv1.2, TLSv1.3 и ssl_certificate.
	8.4. Запускаем контейнер, demon off.
9. MARIADB - dockerfile, mariadb, config 50-server, создание базы данных:
	9.1. Установка. 
	9.2. Создание базы данных:
		9.2.1. host_name должен быть либо %, либо Вы должны задать его принудительно и использовать его имя.
	9.3. Настраиваем 50-server.cnf - закрываем локальные хосты открываем 3306.
	9.4. Запускаем.
10. WORDPRESS - dockerfile, wordpress, php, php-fpm, wp-config, www.conf:
	10.1. Для работы wordpress требуется (https://ru.wordpress.org/about/requirements/)
	10.2. Устанавливаем php и php-fpm (http://xandeadx.ru/blog/php/866):
	10.3. Настраиваем www.conf и цепляем к ngixn (/etc/php/x.x/fpm/pool.d) - (https://www.php.net/manual/ru/install.fpm.configuration.php
	10.4. Устанавливаем wordpress (https://codex.wordpress.org/%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0_WordPress#Using_the_MySQL_Client) - wp-config (https://techlist.top/ustanovka-wordpress-odnoj-knopkoj/)
	10.5. Запускаем (https://linux.die.net/man/8/php-fpm)

Actual Status : finished.
Result : 100%

This is my inception project from the 42 cursus, need help or
you need to translate this article into English write to me.
Contacts here: https://github.com/SavchenkoDV.
