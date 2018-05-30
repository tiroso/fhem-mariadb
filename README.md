<h1>fhem-mariadb</h2>

<h2>Create MariaDB</h2>
<p>Create Volume for persistent data:<br>
<code>docker volume create mariadb</code><br>
Run Docker Container with access to the volume<br>
<code>docker run -d --name=mariadb --restart=always -v /etc/localtime:/etc/localtime:ro -e MYSQL_ROOT_PASSWORD=your-secret-passwort -v mariadb:/var/lib/mysql \<br>
-p 3306:3306 \<br>
mariadb:latest</code>
</p>
<h2>Create phpmyadmin</h2>
<p>This Step is optional. Just for looking to the DB or make some changes</p>
<h4>Same Host - Linked Version</h4>
<p><code>docker run -d --restart=always --name myadmin -v /etc/localtime:/etc/localtime:ro --link mariadb:db -p 8080:80 phpmyadmin/phpmyadmin</code></p>
<h4>Other Host - PMA Version</h4>
<p><code>docker run -d --restart=always --name myadmin -v /etc/localtime:/etc/localtime:ro -e PMA_HOST=&lt;IP or HOSTNAME&gt; -p 8080:80 phpmyadmin/phpmyadmin</code></p>
