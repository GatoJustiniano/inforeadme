# Servidor DNS (BIND)

Configuración de un servidor DNS con zona directa e inversa para el dominio `terresco.online`.

> Reemplaza `67.207.82.x` por la IP real del servidor DNS.

## 1. Zona directa

Crear el archivo de la zona directa:

```
code /var/named/terresco.online.zone
```

## 2. Zona inversa

Crear el archivo de la zona inversa:

```
code /var/named/82.207.67.in-addr.arpa.zone
```

## 3. Cargar las zonas

Registrar la zona directa e inversa en la configuración principal:

```
code /etc/named.conf
```

## 4. Verificar el funcionamiento

Validar la configuración y las zonas:

```
named-checkconf -z /etc/named.conf
```

Consultar cada registro:

```
nslookup terresco.online 67.207.82.x
nslookup dns.terresco.online 67.207.82.x
nslookup mail.terresco.online 67.207.82.x
nslookup ftp.terresco.online 67.207.82.x
```

## Ver también

* [Servidor de correo](docs/linux/servidor-correo.md)
* [Servidor web](docs/linux/servidor-web.md)
