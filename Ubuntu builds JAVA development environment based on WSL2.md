# Ubuntu Builds JAVA Development Environment Based on WSL2

> WSL Documentation Link:[WSL | WSL Install](https://learn.microsoft.com/en-us/windows/wsl/install)

## Install the WSL environment

> Enable the Windows subsystem for Linux: Open powershell and type the follow command

```shell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

> Enable virtualization: open powershell as an administrator and type the follow command

```shell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

> Set WSL default version

```shell
wsl --set-default-version 2
```

> Enable Hyper-v 

```shell
bcdedit /set hypervisorlaunchtype auto
```

> Install the linux distribution

```shell
wsl --install -d Ubuntu
```



## Configure the WSL2

> Create default account and password

> Upgrade the WSL kernel

```shell
wsl --update
```

> Restart and take effect

```shell
wsl -l -shutdown
```

> There are three records

```shell
wsl -l -v
```

> Update package manager if you are Debian (Of course, we used Ubuntu a few steps ahead )

```bash
sudo apt update && sudo apt upgrade
```



## Install and Configure the Docker Desktop

1. Install the docker desktop for windows
2. Register the account and log in
3. Open the software and meanwhile you must log in by the browser
4. Click the settings and configure just for CN mainland users
5. Make sure you have the proxy turned on and it is recommended to turn on TUN mode
6. Docker Desktop runtime does not  need proxy Except for every boot

> ***General***
>
> - [x] Except for every boot
> - [x] Dark
> - [x] Integrated
> - [x] Use the WSL 2 based engine
> - [x] Open Docker Dashboard at startup
> - [x] Use Docker Compose V2General
>
> ***Resources***
>
> - Network: your IP address
> - WSL integration: 
>   - [x] Enable integration with my default WSL distro
>   - [x] Ubuntu
>
> ***Docker Engine***
>
> ```json
> {
>   "builder": {
>     "gc": {
>       "defaultKeepStorage": "20GB",
>       "enabled": true
>     }
>   },
>   "experimental": false,
>   "features": {
>     "buildkit": true
>   },
>   "registry-mirrors": [
>     "https://reg-mirror.qiniu.com/",
>     "https://docker.mirrors.ustc.edu.cn/",
>     "https://hub-mirror.c.163.com/"
>   ]
> }
> ```



## Build a MySQL container

```bash
docker pull mysql:5.7-debian
```

```bash
mkdir /mydata/mysql/
```

```bash
cd /mydata/mysql/
```

```bash
mkdir conf.d
```

```bash
touch my.cnf
```

```bash
vim my.cnf
```

```bash
[client]
default-character-set=utf8

[mysql]
default-character-set=utf8

[mysqld]
init_connect='SET collation_connection = utf8_unicode_ci'
init_connect='SET NAMES utf8'
character-set-server=utf8
collation-server=utf8_unicode_ci
skip-character-set-client-handshake
skip-name-resolve
```

```bash
sudo docker run -p 3306:3306 --name mysql \
-v /mydata/mysql/log:/var/log/mysql \
-v /mydata/mysql/data:/var/lib/mysql \
-v /mydata/mysql/conf.d:/etc/mysql \
-e MYSQL_ROOT_PASSWORD=root \
-d mysql:5.7-debian
```

```bash
docker update mysql --restart=always
```

```bash
docker restart mysql
```

## Build a Redis container

```bash
docker pull redis:7.0.11-bullseye
```

```bash
mkdir -p /mydata/redis/conf
```

```bash
touch /mydata/redis/conf/redis.conf
```

```bash
vim /mydata/redis/conf/redis.conf
```

```bash
appendonly yes
```

```bash
docker run -p 6379:6379 --name redis \
-v /mydata/redis/data:/data \
-v /mydata/redis/conf/redis.conf:/etc/redis/redis.conf \
-d redis:7.0.11-bullseye redis-server /etc/redis/redis.conf
```

```bash
docker update redis --restart=always
```

## Build a Nginx container

```bash
docker pull nginx:1.10
```

```bash
docker run -p 80:80 --name nginx -d nginx:1.10
```

```bash
cd /mydata/nginx
```

```bash
docker container cp nginx:/etc/nginx .
```

```bash
mv /mydata/nginx/nginx /mydata/nginx/conf
```

```bash
docker stop nginx
```

```bash
docker rm nginx
```

```bash
docker run -p 80:80 --name nginx \
-v /mydata/nginx/html:/usr/share/nginx/html \
-v /mydata/nginx/logs:/var/log/nginx \
-v /mydata/nginx/conf:/etc/nginx \
-d nginx:1.10
```

```bash
docker update nginx --restart=always
```

```bash
cd /mydata/nginx/html/
```

```bash
vim index.html
```

