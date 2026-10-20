# Servidor de correo (Sendmail + Dovecot)

Configuración de un servidor de correo con **Sendmail** (SMTP) y **Dovecot** (POP3/IMAP).

## 1. Instalación

Instalar los paquetes necesarios:

```
dnf -y install sendmail sendmail-cf m4 make cyrus-sasl cyrus-sasl-plain
```

Crear un usuario de correo (sin acceso a shell) y asignarle contraseña:

```
useradd -g mail -s /sbin/nologin alvaro.justiniano
passwd alvaro.justiniano
```

Instalar NMAP para revisar los puertos abiertos:

```
dnf -y install nmap
nmap localhost
```

## 2. Configuración de Sendmail

Registrar el dominio:

```
code /etc/mail/local-host-names
```

Definir la lista de control de acceso:

```
code /etc/mail/access
```

Habilitar, iniciar y verificar el servicio:

```
systemctl enable sendmail
systemctl start sendmail
systemctl status sendmail
```

Configurar las funciones de Sendmail:

```
code /etc/mail/sendmail.mc
```

Quitar el `dnl` de las líneas **16, 121, 154 y 165**.

Reiniciar el servicio y verificar que escucha en el puerto 25:

```
systemctl restart sendmail
netstat -ant | grep :25
```

## 3. Control de correo no deseado (spam)

Editar nuevamente `/etc/mail/sendmail.mc` y agregar:

```
FEATURE(dnsbl, `blackholes.mail-abuse.org', `Rechazado - vea http://www.mail-abuse.org/rbl/')dnl
FEATURE(`delay_checks')dnl
FEATURE(dnsbl,`rbl.maps.vix.com',`Rechazado - vea http://www.mail-abuse.org/rbl/')dnl
FEATURE(dnsbl,`dul.mail-abuse.org',`Conexión por línea conmutada - vea http://www.mail-abuse.org/dul/')dnl
FEATURE(dnsbl,`relays.mail-abuse.org',`Relay abierto - vea http://www.mail-abuse.org/rss/')dnl
FEATURE(dnsbl,`input.orbs.org',`Relay abierto - vea http://www.orbs.org/')dnl
```

## 4. Dovecot (acceso al buzón)

Configurar los protocolos de acceso al correo:

```
code /etc/dovecot/dovecot.conf
code /etc/dovecot/conf.d/10-auth.conf
```

Habilitar, iniciar y verificar el servicio:

```
systemctl enable dovecot
systemctl start dovecot
systemctl status dovecot
```

## Ver también

* [Servidor DNS](docs/linux/servidor-dns.md)
