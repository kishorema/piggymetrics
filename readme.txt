delete all docker images: for /F %i in ('docker images -a -q') do docker rmi -f %i

delete all containers: docker system prune

mvn clean install
docker compose -f docker-compose.dev.yml -p piggymetrics up

netstat -na | find "8080"
