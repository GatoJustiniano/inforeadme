-----------------------------------------------------------------------------
title      : Documentación técnica
subtitle   : Apuntes y guías de configuración
nav-group  : temas, new-5, months
nav-width  : 300px
css-header : background:linear-gradient(to bottom right, #06c, #0a8); color:white
menu       :
   Inicio  : ?
   Oscuro  : javascript:darkmode()
   Acerca  : ?page=acerca.md
   GitHub  : https://github.com/GatoJustiniano/inforeadme
-----------------------------------------------------------------------------
<style comment="estilos adicionales">
#header { {{css-header}}  }
#left-panel  { width:{{nav-width}} }
#right-panel { left: calc({{nav-width}} + 20px) }
h1 { border-bottom:1px dotted grey }
.nav-topic   { color: #06c; text-transform: capitalize }
.nav-post a  { color: teal }
.nav-tag  a  { color: #06c }
.nav-month a { color: grey }
.post-date   { font-size:12px; font-weight:400; color:#888 }
.post-title  { font-size:15px; color:#333 }
.post-tags   { padding:4px; font-size:11px; color:green; font-weight:400 }
</style>

<div id="md-post">
# Documentación técnica

Apuntes de configuración de servidores, sistemas y herramientas de desarrollo.
Elige un tema en el menú lateral o en la lista de abajo.

## Linux · Servidores

* 2024/10/05: [Servidor DNS (BIND)](docs/linux/servidor-dns.md) { #linux, #dns }
* 2024/10/05: [Servidor de correo (Sendmail + Dovecot)](docs/linux/servidor-correo.md) { #linux, #correo }
* 2024/10/05: [Servidor web (Apache + PHP)](docs/linux/servidor-web.md) { #linux, #apache }
* 2024/10/18: [Servidor de base de datos (PostgreSQL)](docs/linux/servidor-base-datos.md) { #linux, #postgresql }
* 2024/10/18: [Servidor FTP (vsftpd)](docs/linux/servidor-ftp.md) { #linux, #ftp }

## Odoo

* 2025/02/13: [Configuración del dispositivo biométrico](docs/odoo/configuracion-biometrico.md) { #odoo, #asistencia }

## Laravel

* 2024/12/11: [Comandos frecuentes de Laravel](docs/laravel/comandos-laravel.md) { #laravel, #php }

## Git

* 2024/12/11: [Comandos frecuentes de Git](docs/git/comandos-git.md) { #git }

## Guía del sitio

* 2026/10/19: [Cómo agregar documentos](docs/guia/como-agregar-documentos.md) { #guia }

</div>
