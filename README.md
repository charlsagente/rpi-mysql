# MySQL on Raspberry Pi

### Image Info
This Image based on the Docker official image for mysql
* https://hub.docker.com/_/mysql/
* https://github.com/docker-library/mysql

### How to use this image
* ``` docker pull tobi312/rpi-mysql:5.5 ```
* Optional: ``` mkdir -p /home/pi/.local/share/mysql ```
* ``` docker run --name mysql -d -p 3306:3306 -v /home/pi/.local/share/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw tobi312/rpi-mysql:5.5 ``` 

or build it yourself
* ``` git clone https://github.com/TobiasH87Docker/rpi-mysql && cd rpi-mysql/5.5 ```
* Optional: ``` mkdir -p /home/pi/.local/share/mysql ```
* ``` docker build -t tobi312/rpi-mysql:5.5 . ``` 
* ``` docker run --name mysql -d -p 3306:3306 -v /home/pi/.local/share/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw tobi312/rpi-mysql:5.5 ``` 

### This Image on
* [DockerHub](https://hub.docker.com/r/tobi312/rpi-mysql/)
* [GitHub](https://github.com/TobiasH87Docker/rpi-mysql)
