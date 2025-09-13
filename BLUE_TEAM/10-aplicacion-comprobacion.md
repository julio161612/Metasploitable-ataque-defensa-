# 10. Aplicación y comprobación de cambios

## Comandos

# Aplicar reglas de firewall guardadas
sudo iptables-restore < /root/iptables.rules

# Reiniciar SSH para aplicar configuraciones
sudo systemctl restart ssh

# Verificar puertos abiertos
sudo netstat -tulnp
sudo nmap localhost

# Verificar estado de servicios
sudo systemctl status ssh
sudo systemctl list-units --type=service

## Por qué
- Aplicar todas las reglas de firewall previamente configuradas.
- Confirmar que servicios críticos (SSH) funcionan.
- Comprobar que servicios inseguros están detenidos o bloqueados.

## Diferencia antes / después
- **Antes:** configuraciones por defecto, muchos servicios expuestos.
- **Después:** firewall activo, servicios inseguros detenidos y accesos restringidos.

## Resultado esperado
- Solo puertos seguros accesibles.
- Servicios innecesarios no corriendo.
- Máquina endurecida contra ataques de red y fuerza bruta.
