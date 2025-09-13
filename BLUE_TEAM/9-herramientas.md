# 9. Herramientas adicionales y buenas prácticas

- Usar `chkconfig` o `systemctl list-unit-files` para revisar servicios al arranque.
- Deshabilitar servicios innecesarios: `sudo systemctl disable <servicio>`.
- Instalar herramientas de seguridad: `fail2ban`, `rkhunter`, `chkrootkit`.
- Revisar configuraciones y permisos de archivos críticos.

**Por qué:** Minimizar servicios


