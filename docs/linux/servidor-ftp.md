# Servidor FTP (vsftpd)

Instalación y configuración de un servidor FTP con **vsftpd**.

## 1. Instalación

```
dnf install vsftpd -y
```

## 2. SELinux y firewall

```
setsebool -P allow_ftpd_full_access on
firewall-cmd --permanent --zone=public --add-service=ftp
firewall-cmd --reload
```

## 3. Gestión del servicio

```
systemctl enable vsftpd
systemctl start vsftpd
systemctl status vsftpd
systemctl restart vsftpd
```

## 4. Configuración

Editar la configuración principal y crear la lista de usuarios enjaulados (chroot):

```
code /etc/vsftpd/vsftpd.conf
touch /etc/vsftpd/vsftpd.chroot_list
```

## Ver también

* [Servidor DNS](docs/linux/servidor-dns.md)
