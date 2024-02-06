# 🚀 This is my nuxt-strapi-postgres-nginx-docker project template

This template is designed to develop application on Windows and deploy it on VPS using Docker.

Before you start, check your Docker version with `docker -v`.
You can install it from official site: [Docker](https://docs.docker.com/get-docker/)

## Table of contents

- [Tech stack](#tech-stack)
- [Deploy to production](#deploy-to-production)
- [Important commands](#important-commands)

## Tech stack

### Back-end

- [Strapi](https://docs.strapi.io/)
- [PostgreSQL](https://www.postgresql.org/docs/)

### Front-end

- [Nuxt.js](https://nuxt.com/docs/getting-started/installation)
- [Vuetify](https://vuetifyjs.com/en/getting-started/installation/#installation)

 
## Deploy to production

- backend port has to be updated in:
    - `/backend/Dockerfile`
    - `/backend/Dockerfile.prod`
    - `/nginx/nginx.conf`
    - `/docker-compose.yml`
    - `/docker-compose-prod.yml`
    - `/.env`
- frontend port has to be updated in:
    - `/frontend/Dockerfile`
    - `/frontend/Dockerfile.prod`
    - `/nginx/nginx.conf`
    - `/docker-compose.yml`
    - `/docker-compose-prod.yml`
    - `/.env`
- nginx port has to be update it:
    - `/nginx/nginx.conf`
    - `/docker-compose.yml`
    - `/docker-compose-prod.yml`
-  `/.env` - variables has to be recreated for production mode, change NODE_ENV!

Run command: `docker compose -f docker-compose-prod.yml up -d --build` to start your production mode and put it in the background

## Important commands

To build your project use:
`docker compose up --build` 

To shut down containers use:
`docker compose down`

To shut down containers and additionally clear volumes use:
`docker compose down --volumes`
