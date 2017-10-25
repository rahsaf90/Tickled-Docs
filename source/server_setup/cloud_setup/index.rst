
Digitial Ocean: zer0g-uat-sgp1-01 128.199.154.134
-------------------------------------------------
1. mkvirtualenv prisms_env
2. workon prisms_env
3. pip install -r requirements.txt
4. mkdir -p PRISMSProject/UAT
5. cd PRISMSProject/UAT
6. git clone https://github.com/rahsaf90/PRISMS.git
7. setup release_prisms.sh

///https://www.digitalocean.com/community/tutorials/how-to-install-and-manage-supervisor-on-ubuntu-and-debian-vps
-----------------------------------------------------------------------------------------------------------------

SETUP GUNICORN // THIS IS USED TO HOST PYTHON/DJANGO Live Server files
----------------------------------------------------------------------
https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-14-04-lts
https://simpleisbetterthancomplex.com/tutorial/2016/10/14/how-to-deploy-to-digital-ocean.html
https://cloudsupport.digitalocean.com/s/#none|ka21N000000CosZQAS
**** https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-14-04
SETUP NGINX // THIS IS USED FOR STATIC FILES js/img/html
--------------------------------------------------------


SETUP POSTGRES
--------------
su - postgres
postgres@zer0g-uat-sgp1-01:~$ psql
psql (9.3.10)
Type "help" for help.

postgres=# SELECT usename FROM pg_user;

 psql -U prisms prisms_prod
usename
-------
 postgres
 django
(2 rows)

postgres=# \q
postgres@zer0g-uat-sgp1-01:~$ createuser u_prisms
postgres@zer0g-uat-sgp1-01:~$ createuser u_urbanc^C
postgres@zer0g-uat-sgp1-01:~$ createdb prisms_prod --owner prisms
postgres@zer0g-uat-sgp1-01:~$ psql -c "ALTER USER u_prisms WITH PASSWORD 'prisms_1aug$2017'"

hba_file = '/etc/postgresql/9.3/main/pg_hba.conf'  # host-based authentication file
               # (change requires restart)
ident_file = '/etc/postgresql/9.3/main/pg_ident.conf' # ident configuration file
               # (change requires restart)
               
               
ALTER ROLE prisms SET client_encoding TO 'utf8';
ALTER ROLE prisms SET default_transaction_isolation TO 'read committed';
ALTER ROLE prisms SET timezone TO 'UTC';
