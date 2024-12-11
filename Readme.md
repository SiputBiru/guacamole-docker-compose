# Docker Compose Guacamole

<span>
<img src="https://upload.wikimedia.org/wikipedia/commons/3/31/Apache_Guacamole_logo.png" width="200" alt="Guacamole"/>
<img src="https://raw.githubusercontent.com/docker/compose/main/logo.png" width="200" alt="DockerCompose"/>
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Postgresql_elephant.svg/1200px-Postgresql_elephant.svg.png" width="200" alt="DockerCompose"/>
</span>

## Table of Contents
- [About this Project](#-about-the-project)
- [prerequisite](#-prerequisite)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [To run the container](#️-to-run-the-container)

## 💡 About this Project

<p>
This project establishes Apache Guacamole within my home lab environment using Docker Compose for streamlined deployment and management. Given the lack of a public IP address, a Cloudflare Tunnel is integrated to securely facilitate remote access to the Guacamole interface.
<p>

## 🪶 Prerequisite
- Docker Engine 🐋
- Docker Compose 🐳
Ref: [Docker Installation](https://docs.docker.com/engine/install/)

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

## 🚀 Project Structure

Inside the init file, you'll see default initial database config for postgresql:

```text
/
├── init/
│   └── initdbpsql.sql
├── .env-example
└──  docker-compose.yaml
```

## 🛠️ To run the container

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

4. Open your docker ip address

4. Enjoy! 😁

Note: I have created comment on docker-compose to help making the volumes, you can just delete it if you want.