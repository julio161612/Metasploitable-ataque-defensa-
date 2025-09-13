# 5. Servicios web

## 5.1 Apache
sudo systemctl stop apache2 2>/dev/null || true
sudo systemctl disable apache2 2>/dev/null || true

**Por qué:** Apache 2.2 vulnerable.

**Antes / Después:** Antes activo; después detenido.

**Resultado:** Puerto 80 cerrado.

## 5.2 Tomcat/AJP
sudo systemctl stop tomcat 2>/dev/null || true
sudo systemctl disable tomcat 2>/dev/null || true

**Por qué:** AJP expone vulnerabilidades (Ghostcat).

**Antes / Después:** Antes activo; después detenido.

**Resultado:** Puertos 8009 y 8180 cerrados.
