# 3. VNC (puerto 5900)

## Comando
# Recon
# nmap -sV -p 5900 --script=vnc-info 192.168.10.10 -oN RED_TEAM/outputs/red_vnc_nmap.txt
# Exploit (laboratorio)
# vncviewer 192.168.10.10:5900

## Por qué
VNC sin contraseña permite acceso gráfico completo a la víctima.

## Antes / Después
- Antes: escritorio accesible sin credenciales.  
- Después: acceso restringido o puerto bloqueado.

## Resultado esperado
- RED_TEAM/outputs/red_vnc_nmap.txt con info del servicio.
