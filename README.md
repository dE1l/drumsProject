https://towardsdatascience.com/build-a-back-end-with-postgresql-fastapi-and-docker-7ebfe59e4f06

Требуются переменные окружения:
export GOOGLE_OAUTH_CLIENT_ID=
export GOOGLE_OAUTH_CLIENT_SECRET=
export DATABASE_URL=postgresql+asyncpg://


docker build -t drums-app .
docker run -d --name drums-container --env-file .env -p 80:80 --network="drums-network" drums-app 

docker network create drums-network
docker network connect drums-network drums-container
docker network connect drums-network drums-db

http://0.0.0.0/docs
http://0.0.0.0/redoc
