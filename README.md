## DEVELOPPEMENT

Terminal command from the application's root folder

### To launch the application
- `docker compose -f docker-compose.dev.yml up` => http://localhost/

## PRODUCTION

Terminal commands from the application's root folder

### To instantiate the database, to be done the first time
- `docker volume create dbprod`
- `docker compose -f docker-compose.prod.yml run -d db`
- `docker container exec -it <id_ou_nom> mongosh`
- `use admin`
- `db.auth({user: 'admin', pwd: 'password'})`
- `db.createUser({user: 'thmd', pwd: '123', roles:[{role: 'readWrite', db: 'test'}]})`
- `use test`
- `db.count.insertOne({count: 0});`
- `exit`

### To launch the application
- `docker compose -f docker-compose.prod.yml up` => http://localhost/