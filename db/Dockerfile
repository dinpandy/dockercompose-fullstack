# Use the official MySQL image
FROM mysql:latest

# Add the content of the initialization sql-scripts/ directory to your image
# All scripts in docker-entrypoint-initdb.d/ are automatically executed during container startup
COPY ./scripts/  /docker-entrypoint-initdb.d/
# Set environment variables for MySQL
ENV MYSQL_ROOT_PASSWORD=rootpassword
ENV MYSQL_DATABASE=tecvinson_registration
# Expose MySQL port
EXPOSE 3306

#final:
#docker build --rm=true -t malar17/mysqltecvinson:latest .
#docker run -d -p 3307:3306 --name malarsql  malar17/mysqltecvinson
#docker logs containerID
#docker exec -it malarsql bash
#mysql -uroot -p -- Check database and tables.
#With Volume
#first create volume
#docker volume create test-mysql-data
#docker run --name malarsql -v test-mysql-data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=rootpassword -d malar17/mysqltecvinson


#docker build --rm=true -t dipan7/mysqltecvinson:latest .
#$ docker run -d -p 3306:3306 --name tecvinsonsql \
#-e MYSQL_ROOT_PASSWORD=supersecret dinpandy/mysqltecvinson
#Dynamic
#docker run --name tecvinsonsql -e MYSQL_USER=${MYSQL_USER} -e MYSQL_PASSWORD=${MYSQL_ROOT_PASSWORD} -e MYSQL_DATABASE=${MYSQL_DATABASE} -d dinpandy/mysqltecvinson

#verify
#docker exec -it my-mysql bash
#mysql -uroot -p
#docker start  `docker ps -q -l` # restart it in the background
#docker attach `docker ps -q -l` # reattach the terminal & stdin
#CMD mysql -u $MYSQL_USER -p $MYSQL_PASSWORD $MYSQL_DATABASE < schema.sql



#https://betterprogramming.pub/customize-your-mysql-database-in-docker-723ffd59d8fb
#docker run --name ${CONTAINER_NAME} -e MYSQL_ROOT_PASSWORD=${DB_ROOT_PASSWORD} -e MYSQL_USER=${DB_USER} -e MYSQL_PASSWORD=${DB_USER_PASSWORD} -e MYSQL_DATABASE=${DB_NAME} -d dipan7/mysql

#--rm=true ---Remove intermediate container if successful build
#--force-rm=true --- Remove intermediate container even if it is successful or unsuccessful
#docker build --rm=true -t dipan7/mysqltecvinson:5.6 .
#$ docker run -d --name test-mysql -e MYSQL_ROOT_PASSWORD=strong_password mysql
#Mapping Port
#$ docker run -d --name test-mysql -e MYSQL_ROOT_PASSWORD=strong_password -p 3307:3306 mysql
#https://www.datacamp.com/tutorial/set-up-and-configure-mysql-in-docker
#docker run \
#--name test-mysql \
#-v test-mysql-data:/var/lib/mysql \
#-e MYSQL_ROOT_PASSWORD=strong_password \
#-d mysql

#$ docker volume create test-mysql-data

#To see full list of configuration
#$ docker run -it --rm mysql:tag --verbose --help

#After run, mysql --host=127.0.0.1 --port=3307 -u root -p