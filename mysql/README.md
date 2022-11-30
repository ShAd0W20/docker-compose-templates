# MySQL

## Setup

First of all copy the provided `docker-compose.yml` to the root of your project.

Then create a `.env.local` file in the root of your project and add the following environment variables:

```env
APP_NAME=
DB_PASSWORD=
DB_NAME=
DB_PORT=
```

## Run

To run the docker compose file, you need to run the following command:

```bash
docker-compose --env-file .env.local -f docker-compose.yml up -d
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
