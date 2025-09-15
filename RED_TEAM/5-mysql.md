# 5. MySQL (puerto 3306)

## Comando
# Recon
# nmap -sV -p 3306 --script=mysql-empty-password,mysql-info 192.168.10.10 -oN RED_TEAM/outputs/red_mysql_nmap.txt
# Exploit
# msfconsole -q -x "use auxiliary/scanner/mysql/mysql_login; set RHOSTS 192.168.10.10; set USERNAME root; set PASSWORD ''; run; exit"

## Por qué
Detecta usuarios sin contraseña y accesos débiles.

## Antes / Después
- Antes: acceso root sin contraseña posible.  
- Después: credenciales fuertes, acceso restringido.

## Resultado esperado
- RED_TEAM/outputs/red_mysql_nmap.txt
