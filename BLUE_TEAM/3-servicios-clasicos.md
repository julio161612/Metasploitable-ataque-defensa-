# 3. Servicios clásicos

## 3.1 Telnet
sudo systemctl stop telnet 2>/dev/null || true
sudo systemctl disable telnet 2>/dev/null || true
sudo mv /usr/sbin/telnetd /root/bin_backup/ 2>/dev/null || true

**Por qué:** Telnet envía credenciales en texto claro.

**Antes / Después:** Antes activo; después detenido.

**Resultado:** Puerto 23 cerrado.

## 3.2 FTP (vsftpd y ProFTPD)
sudo systemctl stop vsftpd proftpd 2>/dev/null || true
sudo systemctl disable vsftpd proftpd 2>/dev/null || true
sudo mv /usr/sbin/vsftpd /root/bin_backup/ 2>/dev/null || true
sudo mv /usr/sbin/proftpd /root/bin_backup/ 2>/dev/null || true

**Por qué:** FTP inseguro y sin cifrado.

**Antes / Después:** Antes activo; después inactivo.

**Resultado:** Puertos 21 y 2121 cerrados.

## 3.3 RSH/RLOGIN
sudo systemctl stop rsh rexecd rlogind 2>/dev/null || true
sudo systemctl disable rsh rexecd rlogind 2>/dev/null || true

**Por qué:** Protocolos legacy inseguros.

**Antes / Después:** Antes activo; después deshabilitado.

**Resultado:** Puertos 512 y 513 cerrados.
