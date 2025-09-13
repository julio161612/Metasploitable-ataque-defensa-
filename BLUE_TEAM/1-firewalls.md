# 1. Firewalls

## Comandos
sudo iptables -F
sudo iptables -X
sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
sudo iptables -P OUTPUT ACCEPT

sudo iptables -A INPUT -i lo -j ACCEPT
sudo iptables -A INPUT -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 22 -m conntrack --ctstate NEW -j ACCEPT

for p in 21 23 25 53 111 139 445 512 513 1099 1524 2049 2121 3306 3632 5432 5900 6000 6667 6697 8009 8180 8787; do
  sudo iptables -A INPUT -p tcp --dport $p -j DROP
done

sudo iptables-save | sudo tee /root/iptables.rules

## Por qué
Se establece política "deny by default" para limitar los accesos solo a servicios necesarios (SSH).

## Diferencia antes / después
Antes: todos los puertos estaban accesibles.
Después: solo SSH responde.

## Resultado esperado
Escaneo externo solo muestra el puerto 22 abierto.
