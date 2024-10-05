# Lista de Tareas

## Server DNS

Creación de zona directa  
`code /var/named/terresco.online.zone`

Creación de zona indirecta  
`code /var/named/82.207.67.in-addr.arpa.zone`

Configuración de carga de zona directa e inversa  
`code /etc/named.conf`

Verificación funcionamiento del DNS  
`named-checkconf -z /etc/named.conf`

`nslookup terresco.online 67.207.82.`  
`nslookup dns.terresco.online 67.207.82.`  
`nslookup mail.terresco.online 67.207.82.`  
`nslookup ftp.terresco.online 67.207.82.`  




## Server Mail

- Instalar los siguientes paquetes:  
`dnf –y install sendmail sendmail-cf m4 make cyrus-sasl cyrus- sasl-plain`  

- Crear un usuario y su contraseña:  
`useradd –g mail –s /sbin/nologin alvaro.justiniano`  
`passwd alvaro.justiniano`  


- Instalar NMAP para lograr visualizar los puertos:  
`dnf –y install nmap`  

- Verificar los puertos en localhost:  
`nmap localhost`  

- Ingresamos nuestro dominio en:  
`code /etc/email/local-host-names`  

- Definir la lista de control de acceso:  
`code /etc/mail/access`  

- Arranque de servicio al sistema:  
`systemctl enable sendmail`  

- Iniciar el servicio:  
`systemctl start sendmail`  

- Verificar el servicio:  
`systemctl status sendmail`  

- Configuración de funciones de Sendmail:  
`code /etc/mail/sendmail.mc`  

Borrar dnl de las líneas indicadas. [16,121,154,165]  

- Reiniciar el servicio Sendmail:  
`systemctl restart sendmail`  

- Verificar el puerto de uso de sendmail:  
`netstat -ant | grep :25`  

- Control del correo chatarra (Spam):  
`code /etc/mail/sendmail.mc`  

Agregar  
FEATURE(dnsbl, `blackholes.mail-abuse.org', `Rechazado - vea http://www.mail-abuse.org/rbl/')dnl  
FEATURE(`delay_checks')dnl  
FEATURE(dnsbl,`rbl.maps.vix.com',`Rejected - see http://www.mail-abuse.org/rbl/')dnl   
FEATURE(dnsbl,`dul.mail-abuse.org',`Dialup - see http://www.mail-abuse.org/dul/')dnl   
FEATURE(dnsbl,`relays.mail-abuse.org',`Open relay - see http://www.mail-abuse.org/rss/')dnl   
FEATURE(dnsbl,`input.orbs.org',`Open relay - see http://www.orbs.org/')dnl  


- Protocolos para acceder hacia el correo:  
`code /etc/dovecot/dovecot.conf`  
`code /etc/dovecot/conf.d/10-auth.conf`  

- Arrancar el servicio Dovecot(POP3):  
`systemctl enable dovecot`  
`systemctl start dovecot`  
`systemctl status dovecot`  








