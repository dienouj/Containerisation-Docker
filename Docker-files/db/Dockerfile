FROM mysql:8.0.33
LABEL "Project"="Vprofile"
LABEL "Maintainer"="Jouneid"
# This Dockerfile sets up a MySQL database server.
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql docker=entrypoint-initdb.c/db_backup.sql
# The database is initialized with a backup SQL file.