# MySQL on Raspberry Pi / armhf

This is a port of the official MySQL image https://hub.docker.com/_/mysql/ for Raspberry Pi / armhf.

###  `Dockerfile` links
-	[`latest` (*Dockerfile*)](https://github.com/charlsagente/rpi-mysql/blob/master/5.5/Dockerfile)

![logo](https://raw.githubusercontent.com/docker-library/docs/master/mysql/logo.png)

### How to use this image
* ``` docker pull charlsagente/raspberry-mysql ```

### Usage in compose file
```yaml
version: '3.7'

services:

  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb

  db:
    image: charlsagente/raspberry-mysql
    #build: #Uncomment build if you want to build the image by your self
      #context: .
      #dockerfile: Dockerfile
    volumes:
      - db-data:/var/lib/mysql/data
    restart: always
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: '1'

volumes:
  db-data:
```

or build it yourself
* ``` $ git clone https://github.com/charlsagente/rpi-mysql/ && cd rpi-mysql ```
* ``` $ docker build -t rpi-mysql ./5.5/ ```
* Optional: ``` $ mkdir -p /home/pi/.local/share/mysql ```
* ``` $ docker run --name mysql -d -p 3306:3306 -v /home/pi/.local/share/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw tobi312/rpi-mysql ```



### This Image on
* [DockerHub](https://hub.docker.com/r/charlsagente/raspberry-mysql)
* [GitHub](https://github.com/charlsagente/rpi-mysql/)
