# PostgreSQL

## Setup

First of all copy the provided `docker-compose.yaml` to the root of your project.

Then create a `.env.local` file in the root of your project and add the following environment variables:

```env
POSTGRES_DB=
POSTGRES_USER=
POSTGRES_PASSWORD=
```

## Run

To run the docker compose file, you need to run the following command:

```bash
docker-compose --env-file .env.local -f docker-compose.yaml up -d
```

## Notes

Once you run the docker compose file, you will be able to access the database from your browser using the following URL:

```bash
http://localhost:8080
```

You can also access the database from your code using the following URL:

```bash
postgresql://${POSTGRES_USER}:${POSTGRES_PASSWORD}@localhost:5432/${POSTGRES_DB}
```
