# 1. SMTP

## Comando
# Escaneo con nmap y scripts SMTP (enumeración de usuarios y comandos soportados)
nmap -sV -p 25 --script=smtp-enum-users,smtp-commands 192.168.10.10 -oN RED_TEAM/outputs/red_smtp_nmap.txt

# Conexión manual para probar VRFY/EXPN (interactiva)
# nc 192.168.10.10 25
# En la sesión SMTP:
# HELO lab.local
# VRFY root
# EXPN postmaster
# QUIT

# Metasploit (recon y exploit en laboratorio)
# msfconsole -q -x "use auxiliary/scanner/smtp/smtp_enum; set RHOSTS 192.168.10.10; run; exit"

## Por qué
VRFY/EXPN pueden revelar cuentas de correo/usuarios del sistema.
Un servidor abierto (relay) puede ser abusado para enviar spam o camuflar campañas de phishing — en laboratorio se usa para demostrar impacto.

## Antes / Después
- Antes: servidor SMTP en Metasploitable puede responder a VRFY/EXPN y/o aceptar relay.
- Después (si se mitiga): VRFY/EXPN deshabilitados; relay cerrado, sólo clientes autorizados pueden enviar.

## Resultado esperado
- RED_TEAM/outputs/red_smtp_nmap.txt con resultados de nmap.
- Si relay abierto en laboratorio: evidencia de envío (logs del servidor / mail queue).
- Registra timestamps y salidas para el informe.
