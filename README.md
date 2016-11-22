# Dockerfile for MySQL on Raspberry Pi (based on the Docker official image for mysql)
* https://hub.docker.com/_/mysql/
* https://github.com/docker-library/mysql

Use:
* ``` git clone REPOSITORY && cd rpi-mysql/5.5 ```
* Optional: ``` mkdir -p /home/pi/.local/share/mysql ```
* ``` docker build -t rpi-mysql:5.5 . ``` 
* ``` docker run --name mysql -d -p 3306:3306 -v /home/pi/.local/share/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw rpi-mysql:5.5 ``` 
