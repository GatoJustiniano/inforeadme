# Configuración del dispositivo biométrico

Conexión de un reloj biométrico (por ejemplo ZKTeco) con el módulo de **Asistencias** de Odoo.

## 1. Abrir el puerto en el router

En el router del proveedor de internet, crear una regla de **redirección de puertos** (*port forwarding*) hacia la IP local del dispositivo biométrico:

```
Puerto: 4370
```

## 2. Registrar el dispositivo en Odoo

Ir a **Asistencias → Información de dispositivos → Nuevo** y completar:

| Campo | Valor |
|-------|-------|
| Nombre | Lo más descriptivo posible (ej. "Reloj entrada principal") |
| IP / Dominio | De preferencia el dominio |
| Puerto | El mismo asignado en el router (`4370`) |
| Protocolo | TCP |

## 3. Probar la conexión

Desde el módulo de Asistencias, verificar que Odoo se conecta con el dispositivo y descarga las marcaciones.
