# Servidor web (Apache + PHP)

Configuración de Apache con PHP, un directorio publicado y acceso protegido con usuario y contraseña.

## 1. Instalación

```
dnf -y install httpd php php-mysqlnd php-pgsql
```

Permisos de SELinux necesarios:

```
setsebool -P httpd_can_sendmail 1
setsebool -P httpd_read_user_content 1
setsebool -P httpd_can_network_connect_db 1
```

Instalar firewalld y habilitar HTTP:

```
dnf install firewalld
firewall-cmd --add-service=http --permanent
firewall-cmd --reload
```

## 2. Ocultar la versión de Apache

Agregar al final de `/etc/httpd/conf/httpd.conf`:

```
ServerSignature off
ServerTokens Prod
```

Reiniciar el servicio:

```
systemctl restart httpd.service
```

## 3. Publicar un directorio

Crear la carpeta, darle contexto de SELinux y permisos:

```
mkdir -p /var/www/midir
chcon -t httpd_sys_content_t /var/www/midir
chmod 755 /var/www/midir
```

Crear el archivo de configuración del directorio:

```
code /etc/httpd/conf.d/midir.conf
```

```
Alias /midir /var/www/midir
<Directory "/var/www/midir">
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Order Allow,Deny
    Allow from All
    Require local
    Require all granted
</Directory>
```

Reiniciar el servicio:

```
systemctl restart httpd.service
```

## 4. Restringir el acceso con contraseña

Crear el archivo `.htaccess`:

```
code /var/www/midir/.htaccess
```

```
AuthName "Solamente usuarios autorizados"
AuthType Basic
Require valid-user
AuthUserFile /var/www/midir/.claves
```

Crear el archivo de credenciales y el usuario (pedirá la contraseña):

```
touch /var/www/midir/.claves
htpasswd /var/www/midir/.claves grupo10sc
```

> No documentes contraseñas reales en este sitio: es público.

## Ver también

* [Servidor de base de datos](docs/linux/servidor-base-datos.md)
