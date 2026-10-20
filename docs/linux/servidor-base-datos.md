# Servidor de base de datos (PostgreSQL)

Instalación y configuración de PostgreSQL con acceso remoto por contraseña.

## 1. Instalación

```
dnf install postgresql postgresql-server -y
```

## 2. Configuración inicial

Inicializar la base de datos y asignar contraseña al usuario `postgres`:

```
postgresql-setup --initdb
systemctl enable --now postgresql
su - postgres
psql -c "alter user postgres with password 'TU_CONTRASEÑA'"
```

## 3. Gestión del servicio

```
systemctl enable postgresql
systemctl start postgresql
systemctl status postgresql
systemctl restart postgresql
```

## 4. Archivo principal y firewall

```
firewall-cmd --add-service=postgresql --permanent
firewall-cmd --reload
code /var/lib/pgsql/data/postgresql.conf
```

## 5. Control de acceso

Editar:

```
code /var/lib/pgsql/data/pg_hba.conf
```

Agregar alrededor de la línea 115:

```
# ADMIN:
host    all             all             0.0.0.0/0               password
# Grupo:
host    db_terresco     all             0.0.0.0/0               password
```

## 6. Roles y base de datos

1. Crear el rol `grupo10sc`.
2. Crear la base de datos `db_terresco`.
3. Asignar el rol a la base de datos.

## Ver también

* [Servidor web](docs/linux/servidor-web.md)
