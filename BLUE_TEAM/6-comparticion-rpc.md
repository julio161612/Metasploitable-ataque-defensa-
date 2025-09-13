# 6. Servicios de compartición y RPC

## 6.1 Samba
sudo cp /etc/samba/smb.conf /root/smb.conf.backup 2>/dev/null || true
sudo mv /etc/samba/smb.conf /etc/samba/smb.conf.disabled 2>/dev/null || true
sudo systemctl stop smbd nmbd 2>/dev/null || true
sudo systemctl disable smbd nmbd 2>/dev/null || true

**Por qué:** Evita compartir directorios sin control.

**Antes / Después:** Antes compartía recursos; después detenido.

**Resultado:** Puertos 139 y 445 cerrados.

## 6.2 NFS/RPC
sudo cp /etc/exports /root/exports.backup 2>/dev/null || true
sudo truncate -s 0 /etc/exports
sudo systemctl stop nfs-server rpcbind 2>/dev/null || true
sudo systemctl disable nfs-server rpcbind 2>/dev/null || true

**Por qué:** Evita montaje remoto de sistema de archivos.

**Antes / Después:** Antes activo; después detenido.

**Resultado:** Puertos 111 y 2049 cerrados.
