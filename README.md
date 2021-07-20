# inception_School21_Ecole42
This project aims to broaden your knowledge of system administration by using Docker. You will virtualize several Docker images, creating them in your new personal virtual machine.

Предисловие:
---------------------------------------------------------------------------------------------------------------------------------

Данный мануал - это мои пошаговые действия, каким образом я действовал и что читал. Все ссылки, которые здесь предоставлены - это не полная информация, так же я пользовался StackOverflow и другими источниками. Вместе с тем данные ссылки мне дали общее понимание, как все устроено и искать информацию стало просто.

---------------------------------------------------------------------------------------------------------------------------------

<img alt="visub"  src="https://user-images.githubusercontent.com/78852244/126368155-d1450b9c-82f4-41b4-a41d-28ebe119f6b6.png">

Реализация VirtualBox - Ubuntu 20.04, Containers - debian:buster:
---------------------------------------------------------------------------------------------------------------------------------
1. <a href="https://losst.ru/kak-polzovatsya-virtualbox#2_%D0%A1%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5_%D0%B2%D0%B8%D1%80%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9_%D0%BC%D0%B0%D1%88%D0%B8%D0%BD%D1%8B">Создаем виртуалуальную машину Ubuntu.</a>
2. <a href="https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-ru">Устанавливаем Docker.</a>
3. <a href="https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-ru">Устанавливаем Docker-Compose.</a>
4. Устанавливаем VIM, MAKE, GIT и другик программы, плагины необходимые для работы.
5. Меняем в Ubuntu хосты: vim /etc/hosts далее меняем localhost на ****.42.fr.
6. Создаем Makefile:<br>
&emsp; 6.1. Задаем общие настройки Makefile - для удобства сборки и пересборки контейнеров:<br>
&emsp; &emsp; 6.1.1. Запуск контейнеров.<br>
&emsp; &emsp; 6.1.2. Отключение.<br>
&emsp; &emsp; 6.1.3. Удаление и очистка всего.
7. <a href="https://dker.ru/docs/docker-compose/compose-file-reference">Создаем файл docker-compose.yml:</a><br>
&emsp; 7.1. Создаем network. <br>
&emsp; 7.2. <a href="https://docs.docker.com/storage/volumes/">Создаем volumes</a> + еще одна <a href="https://github.com/compose-spec/compose-spec/blob/master/spec.md#volumes-top-level-element">ссылка.</a><br>
&emsp; 7.3. <a href="https://dker.ru/docs/docker-compose/compose-file-reference">Создаем команды на сборку контейнеров - services. Не забываем подключить network и volume.</a><br>
8. NGINX - dockerfile, nginx, config, openssl:<br>
&emsp; 8.1. Устновливем nginx и openssl.<br>
&emsp; 8.2. Подписываем сертификат openssl.<br>
&emsp; 8.3. Изменияем конфиг nginx: etc/nginx/sites-enabled/defaul. <a href="https://serveradmin.ru/ustanovka-i-nastrojka-nginx/">Ссылка для общего понимания.</a> <br> 
&emsp; В <a href="https://nginx.org/ru/docs//">документации</a> все написанно, прийдеться покопаться:<br>
&emsp; &emsp; 8.3.1. <a href="https://nginx.org/ru/docs/beginners_guide.html">Синтаксис конфига.</a><br>
&emsp; &emsp; 8.3.2. Ищем info в интернете, как добавить в config nginx: ssl_portocol TLSv1.2, TLSv1.3 и ssl_certificate.<br>
&emsp; 8.4. Запускаем контейнер, demon off.
9. MARIADB - dockerfile, mariadb, config 50-server, создание базы данных:<br>
&emsp; 9.1. Установка. <br>
&emsp; 9.2. Создание базы данных:<br>
&emsp; &emsp; 9.2.1. host_name должен быть либо %, либо Вы должны задать его принудительно и использовать его имя.<br>
&emsp; 9.3. Настраиваем 50-server.cnf - закрываем локальные хосты открываем 3306.<br>
&emsp; 9.4. Запускаем.
10. WORDPRESS - dockerfile, wordpress, php, wp-config, php-fpm, ввв.conf: <br>
&emsp; 10.1. <a href="https://ru.wordpress.org/about/requirements/">Для работы wordpress требуется.</a> <br>
&emsp; 10.2. <a href="http://xandeadx.ru/blog/php/866">Устанавливаем php и php-fpm.</a><br>
&emsp; 10.3. Настраиваем <a href="https://www.php.net/manual/ru/install.fpm.configuration.php">ввв.conf</a> и цепляем к ngixn: /etc/php/x.x/fpm/pool.d<br>
&emsp; 10.4. <a href="https://codex.wordpress.org/%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0_WordPress#Using_the_MySQL_Client) - wp-config (https://techlist.top/ustanovka-wordpress-odnoj-knopkoj/">Устанавливаем wordpress: /etc/php/x.x/fpm/pool.d</a>  <br>
&emsp; 10.5. <a href="https://linux.die.net/man/8/php-fpm">Запускаем.</a>
---------------------------------------------------------------------------------------------------------------------------------
Actual Status : finished.
Result : 100%

This is my inception project from the 42 cursus, need help or
you need to translate this article into English write to me.
Contacts here: https://github.com/SavchenkoDV.
