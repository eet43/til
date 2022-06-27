# Mysql 초기 세팅

자꾸 까먹고 찾아보기 귀찮아서 여기다가 한 번에 정리하려고 한다.<br><br>

<br><br>

mysql 경로접근 : cd /usr/local/mysql/bin <br><br>
=> 원래 환경변수 설정해줘야 하는데 너무 귀찮다.<br><br>

mysql 실행(root) : ./mysql -u root -p <br><br>

mysql 유저 만들기 : create user devit@localhost identified by '1234';<br><br>

mysql 데이터베이스 만들기(한글 설정까지) : create database devit_user default character set utf8;<br><br>

mysql 유저에게 (모든)권한 주기 : grant all privileges on devit_user.* to devit@localhost;<br><br>
