# Docker compose Guacamole using Posgresql
<img src="https://upload.wikimedia.org/wikipedia/commons/3/31/Apache_Guacamole_logo.png" width="200" />
<img src="https://www.docker.com/wp-content/uploads/2023/08/logo-guide-logos-1.svg" width="100"/>

🧞 To run the container

1. clone the repo 

2. Change the .env-example to .env and add your cloudflare token

3. Run the container
```sh
docker compose up -d
```

4. Enjoy! 😁

Note: I have created comment on docker-compose to help for making the volumes, you can just delete it if you want.

## 🚀 Project Structure

Inside the init file, you'll see default initial database config for postgresql:

```text
/
├── init/
│   └── initdbpsql.sql
├── .env-example
└──  docker-compose.yaml
```