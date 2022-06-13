# Mysql root 비번 까먹을 때

오늘 이거 때문에 삽질아닌 삽질을 너무 했다. <br><br>

1. 시스템 환경설정 -> mysql -> 중지. <br><br>
2. 첫 번째 터미널에서 안전모드 실행. <br>
`sudo /usr/local/mysql/bin/mysqld_safe --skip-grant-tables` <br><br>
3. 두 번째 터미널에서 mysql 접속.<br>
`sudo /usr/local/mysql/bin/mysql -u root`<br><br>
4. root 비밀번호 없애기.<br>
`UPDATE mysql.user SET authentication_string=null WHERE User='root';`<br>
`FLUSH PRIVILEGES;`<br>
`exit;`<br><br>
5. 재접속 후 비밀번호 바꾸기.<br>

`sudo /usr/local/mysql/bin/mysql -u root`<br>

`ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY '바꿀 비밀번호';`<br>

`FLUSH PRIVILEGES;`<br>

`exit;`<br><br>

6. 재시작.

`sudo /usr/local/mysql/support-files/mysql.server restart`<br><br>

