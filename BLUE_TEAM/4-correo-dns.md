# 4. Servicios de correo y DNS

## 4.1 SMTP
sudo iptables -A INPUT -p tcp --dport 25 -j DROP

**Por qué:** Evita relay abierto y spam.

**Antes / Después:** Antes accesible; después bloqueado.

**Resultado:** Puerto 25 cerrado.

## 4.2 DNS
sudo iptables -A INPUT -p tcp --dport 53 -j DROP
sudo iptables -A INPUT -p udp --dport 53 -j DROP

**Por qué:** Evita ataques de amplificación DNS.

**Antes / Después:** Antes accesible; después bloqueado.

**Resultado:** Puerto 53 cerrado.
