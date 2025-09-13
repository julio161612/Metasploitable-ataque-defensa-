# 8. Servicios remotos y otros

## 8.1 DistCC
sudo systemctl stop distccd 2>/dev/null || true
sudo systemctl disable distccd 2>/dev/null || true

**Por qué:** Evita exploits de ejecución remota.

**Antes / Después:** Antes activo; después detenido.

**Resultado:** Puerto 3632 cerrado.

## 8.2 VNC/X11
sudo iptables -A INPUT -p tcp --dport 5900 -j DROP
sudo iptables -A INPUT -p tcp --dport 6000 -j DROP

**Por qué:** Acceso gráfico remoto inseguro.

**Antes / Después:** Antes accesible; después bloqueado.

**Resultado:** Puertos 5900 y 6000 cerrados.

## 8.3 Bindshell
sudo iptables -A INPUT -p tcp --dport 1524 -j DROP

**Por qué:** Shell abierto para root.

**Antes / Después:** Antes activo; después bloqueado.

**Resultado:** Puerto 1524 cerrado.

## 8.4 IRC
sudo iptables -A INPUT -p tcp --dport 6667 -j DROP
sudo iptables -A INPUT -p tcp --dport 6697 -j DROP

**Por qué:** Evita que la máquina sea usada como botnet.

**Antes / Después:** Antes accesible; después bloqueado.

**Resultado:** Puertos 6667 y 6697 cerrados.
