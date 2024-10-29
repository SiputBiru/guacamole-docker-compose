# Docker Compose Guacamole

<span>
<img src="https://upload.wikimedia.org/wikipedia/commons/3/31/Apache_Guacamole_logo.png" width="200" alt="Guacamole"/>
<img src="https://raw.githubusercontent.com/docker/compose/main/logo.png" width="200" alt="DockerCompose"/>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Postgresql_elephant.svg/1200px-Postgresql_elephant.svg.png" width="200" alt="DockerCompose"/>
</span>

## Table of Contents
- [About the Project](#about-the-project)
- [🎮 Features](#features)
- [🧞 To run the container](#installation)

## About the Project

<p>
I want to use guacamole for my home lab but i want to use docker compose for my convinient
On this docker compose i add cloudflare tunnel cause i don't really have ip public on my home lab 
<p>


## 🎮 Features

- Volumes: (optional) <br>
    a. guacwebconfig: <br>
        - for backup guacamole config file <br>
    b. guac-dbdata: <br>
        - database backup volumes <br>

- Network: <br>
    a. guac-net: <br>
        - for the guacamole network <br>
    b. tunnel: <br>
        - for cloudflare tunnel network <br>

- Services: <br>
    a. **Cloudflare Tunnel** <br>
        - For tunneling <br>
    b. **guacd** <br>
        - Provides the guacd daemon, built from the released guacamole-server source with support for VNC, RDP, SSH, telnet, and Kubernetes <br>
    c. **guacamole** <br>
        - Provides the Guacamole web application running within Tomcat 8 with support for WebSocket. The configuration necessary to connect to guacd, MySQL, PostgreSQL, LDAP, etc. will be generated automatically when the image starts based on Docker links or environment variables. <br>
    d. **postgresql** <br>
        - Provides the database that Guacamole will use for authentication and storage of connection configuration data. <br>

I adding cloudflare tunnel for my project purposes you can remove it if you want 😊

## 🧞 To run the container

1. Clone the Repo 
```bash
git clone git@github.com:SiputBiru/guacamole-docker-compose.git
```

2. Change the .env-example to .env and add your cloudflare token
```text
SECRET_TOKEN=YOURCLOUDFLARETOKEN
```

3. Run the container
```sh
docker compose up -d
```

4. Enjoy! 😁

Note: I have created comment on docker-compose to help making the volumes, you can just delete it if you want.

## 🚀 Project Structure

Inside the init file, you'll see default initial database config for postgresql:

```text
/
├── init/
│   └── initdbpsql.sql
├── .env-example
└──  docker-compose.yaml
```

