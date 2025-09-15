# 2. HTTP (puerto 80)

## Comando
# Recon con nmap
# nmap -sV -p 80 --script=http-enum,http-vuln* 192.168.10.10 -oN RED_TEAM/outputs/red_http_nmap.txt
# Nikto
# nikto -host http://192.168.10.10 -output RED_TEAM/outputs/red_nikto.txt
# Gobuster
# gobuster dir -u http://192.168.10.10 -w /usr/share/wordlists/dirb/common.txt -o RED_TEAM/outputs/red_gobuster.txt
# SQLi con sqlmap (si encuentras parámetros)
# sqlmap -u "http://192.168.10.10/vuln.php?id=1" --batch --dbs -o RED_TEAM/outputs/sqlmap_output.txt

## Por qué
Detecta directorios ocultos, archivos sensibles y posibles vulnerabilidades web (RCE, LFI, SQLi).

## Antes / Después
- Antes: servidor web expone archivos de prueba, directorios y apps vulnerables.  
- Después: Blue Team parchea y limita accesos.

## Resultado esperado
- RED_TEAM/outputs/red_http_nmap.txt, red_nikto.txt, red_gobuster.txt, sqlmap_output.txt
