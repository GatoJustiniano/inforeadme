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






