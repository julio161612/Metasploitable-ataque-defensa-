# 11. ProFTPD (puerto 2121)

## Comando
# Recon
# nmap -sV -p 2121 192.168.10.10 -oN RED_TEAM/outputs/red_proftpd_nmap.txt

## Por qué
Detecta vulnerabilidades históricas (ej. mod_copy) y permite pruebas de exploit en laboratorio.

## Antes / Después
- Antes: servicio vulnerable activo.  
- Después: servicio actualizado o cerrado.

## Resultado esperado
- RED_TEAM/outputs/red_proftpd_nmap.txt con banner y versión vulnerable.
