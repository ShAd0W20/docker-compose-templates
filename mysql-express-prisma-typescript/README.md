# MySQL + Node + Express + Prisma + TypeScript

## Setup

First you need to install the dependencies:

```bash
npm install -D nodemon
```

Create a nodemon.json file in the root of the project:

```json
{
  "verbose": true,
  "watch": ["src/**/*.ts"],
  "execMap": {
    "ts": "node --inspect=0.0.0.0:9229 --nolazy -r ts-node/register"
  }
}
```

Create a .env file in the root of the project:

```env
MYSQL_ROOT_PASSWORD=
DATABASE_URL=mysql://YOUR_DB_USER:YOUR_DB_PASSWORD@localhost/YOUR_DATABASE_NAME
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
"dev:docker": "nodemon --legacy-watch src/index.ts"
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
