# MySQL + NodeJS express

## Setup

Copy the docker-compose.yml and the Dockerfile to the root of your project.

Install nodemon in order to restart the server when you make changes to the code:

```bash
npm install -D nodemon
```

Create a nodemon.json file in the root of the project:

```json
{
  "verbose": true,
  "watch": ["src/**/*.js"]
}
```

Create a .env.local file in the root of the project:

```env
APP_NAME=
DB_PASSWORD=
DB_NAME=
DB_PORT=
```

In case you are using JWT authentication, you need to add the following environment variables:

```env
AUTH_KEY=
```

And in the docker-compose.yml file, you need to add the following environment variables in the web service under the environment section:

```yml
AUTH_KEY: ${AUTH_KEY}
```

## Run

Make sure to add this command to your package.json file under the scripts section:

```json
"dev:docker": "nodemon --legacy-watch src/index.js"
```

To run the docker compose file, you need to run the following command:

```bash
docker-compose --env-file .env.local up -d
```

## Notes

Once you run the docker compose file, you will be able to access the database from your browser using the following URL:

```bash
http://localhost:8080
```

You can also access the database from your code using the following URL:

```bash
mysql://root:${DB_PASSWORD}@localhost:${DB_PORT}/${DB_NAME}
```
