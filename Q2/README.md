after initializing the containers with
```
docker-compose up -d
```
you need to go inside containers my-postgres1 and my-postgres2
```
sudo docker exec -it my-postgres2 bash
```
then locate to the folder `/fake-data` and execute the following
```
psql -U myuser -d mydb -f ticket.sql
```
to import csvs, you have to execute
```
psql -U myuser -d mydb -c "\copy [table_name]
FROM '[corresponding_csv]' 
DELIMITER ',' 
CSV HEADER;"
```
in order of ticket.sql

the same thing can be applied for the postgres database related to auth.

## dbeaver

to install dbeaver on your system follow [this](https://computingforgeeks.com/install-and-configure-dbeaver-on-ubuntu-debian/) guide.



## problems

the persistent volumes were not deleted with `docker-compose down`

to fix it we used
```
docker-compose down -v
```