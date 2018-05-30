<h1>fhem-mariadb</h2>

<h2>Create MariaDB</h2>
<p>Create Volume for persistent data:<br>
<code>docker volume create mariasql</code><br>
Run Docker Container with access to the volume<br>
<code>docker run -d \<br>
--name=mariadb \<br>
--restart=always \<br>
-v /etc/localtime:/etc/localtime:ro \<br>
-e MYSQL_ROOT_PASSWORD=your-secret-passwort \<br>
-v /storage/mariadb:/var/lib/mysql \<br>
-p 3306:3306 \<br>
mariadb:latest</code>
</p>

docker run -d \
--restart=always \
--name myadmin \
-v /etc/localtime:/etc/localtime:ro \
--link mariadb:db \
-p 8080:80 \
phpmyadmin/phpmyadmin
