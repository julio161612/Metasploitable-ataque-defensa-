# 7. Bases de datos

## 7.1 MySQL
sudo cp /etc/mysql/my.cnf /root/my.cnf.backup 2>/dev/null || true
sudo sed -i 's/^bind-address.*/bind-address = 127.0.0.1/' /etc/mysql/my.cnf
sudo service mysql restart

**Por qué:** Limita acceso solo a localhost.

**Antes / Después:** Antes accesible desde fuera; después localhost únicamente.

**Resultado:** Puerto 3306 cerrado externamente.

## 7.2 PostgreSQL
sudo cp /etc/postgresql/8.3/main/postgresql.conf /root/postgresql.conf.backup 2>/dev/null || true
sudo sed -i "s/^#listen_addresses.*/listen_addresses='localhost'/" /etc/postgresql/8.3/main/postgresql.conf
sudo service postgresql restart

**Por qué:** Restringe PostgreSQL a localhost.

**Antes / Después:** Antes escuchaba en todas las interfaces; después solo local.

**Resultado:** Puerto 5432 cerrado externamente.
