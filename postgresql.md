
`sudo -u postgres psql`

## List database
`\l`

## List user
`\du`

## Connect to database
`\c database_name`

## Folder config
`cd /var/lib/pgsql/data/`

## File Config
`postgresql.conf`  
`pg_hba.conf`


## Restart service
`sudo systemctl restart postgresql`

## Add access port
`firewall-cmd --get-active-zones`  
`firewall-cmd --zone=public --add-port=5432/tcp --permanent`  
`firewall-cmd --reload`

```
=========================pg_hba.conf===================
local   all             all                                     ident
# IPv4 local connections:
host    all             all             127.0.0.1/32            md5
host    all             all             0.0.0.0/0               trust
# IPv6 local connections:
host    all             all             ::1/128                 ident
# Allow replication connections from localhost, by a user with the
# replication privilege.
local   replication     postgres                                peer
host    replication     postgres        127.0.0.1/32            md5
host    replication     postgres        ::1/128                 md5

```

```
===================postgresql.conf========================
data_directory = '/var/lib/pgsql/data' 
listen_addresses = '*'  
port = 5432  

```