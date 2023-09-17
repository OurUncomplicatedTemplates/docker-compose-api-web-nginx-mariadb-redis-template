# Project Template
All you need to do after using this template is adding 2 submodules, a backend at `/api` and a frontend at `/web`.

## Docker containers
All the containers run on their own seperated network. The network is configured in a bridge configuration


#### Development
##### Install
- Add .env files

```bash
pnpm install --shamefully-hoist
```

##### Start
```bash
docker-compose up --build -d
```
```bash
pnpm -r run migrate:dev
```
```bash
pnpm -r run dev
```

##### Stop
```bash
docker-compose down
```

#### General
##### Remove
Remove docker containers, remember to shutdown first.
```bash
docker-compose rm
```

##### Prune
Remove all unused container volumes.
```bash
docker volume prune
```

##### Logs
```bash
docker-compose logs -f mariadb
```
```bash
docker-compose logs -f redis
```

##### SSH
```bash
docker-compose exec mariadb /bin/bash
```
```bash
docker-compose exec redis /bin/bash
```

### mariadb
This container is running our mariadb server.  

Port 3306 is exposed to the host.  

### redis
The container running our redis caching server.  

Port 6379 is exposed to the host.