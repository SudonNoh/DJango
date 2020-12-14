# MARIADB & Django 연동

---------------------------------------------------------------------------------------------

## 1. Start the MARIA DB server on Linux

MariaDB 시작  
systemctl start mariadb or systemctl restart mariadb  
  
MariaDB 상시 가동  
systemctl enable mariadb  

MariaDB 가동 확인  
systemctl status mariadb  

---------------------------------------------------------------------------------------------

## 2. MARIA DB 관리자 접속 방법

mysql -h localhost -u root -p

---------------------------------------------------------------------------------------------

## 3. modify settings.py

```python
DATABASES = {
    'default': {

        1) 'ENGINE': 'django.db.backends.mysql',
        2) 'NAME': 'DB_NAME',
        3) 'USER': 'USER_ID',
        4) 'PASSWORD':'PASSWORD'
        5) 'HOST':'MARIADB_SERVER_IP',
        6) 'PORT':'MARIADB_PORT'

    }
}
```

      1) 'ENGINE': splite3 > mysql 로 변경
      2) 'NAME': DATABASE 이름 입력
          - 확인 방법: SHOW DATABASES;
      3) 'USER': SERVER 접속 시에 USER로 root 이용 불가, 새로운 DB USER 생성 후 입력
          - USE DB_NAME;
          - CREATE USER 'USER_ID'@'%' identified by 'PASSWORD'; USER 생성
          - GRANT ALL PRIVILEGES ON DB_NAME.* TO 'USER_ID'@'%'; USER 권한 부여
          - SHOW GRANTS FOR 'USER_ID'@'%'; USER 권한 부여 확인
          - FLUSH RIVILEGES; USER 권한 부여 확정
      4) 'PASSWORD': 
          - 'USER_ID' 를 만들 때 사용한 'PASSWORD'를 입력
      5) 'HOST':
          - MARIADB 의 SERVER IP를 확인
          - IFCONFIG
      6) 'PORT':
          - SHOW GLOBAL VARIABLES LIKE 'PORT';
---------------------------------------------------------------------------------------------

## 4. manage.py migrate

python3 manage.py migrate

