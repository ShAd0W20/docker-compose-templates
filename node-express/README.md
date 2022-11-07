# NodeJS express

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

## Run

Make sure to add this command to your package.json file under the scripts section:

```json
"dev:docker": "nodemon --legacy-watch src/index.js"
```

To run the docker compose file, you need to run the following command:

```bash
docker-compose --env-file .env.local up -d
```
