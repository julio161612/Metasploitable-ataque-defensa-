# 2. Mitigación de fuerza bruta

## Comandos
sudo cp /etc/ssh/sshd_config /root/sshd_config.bak
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin no/' /etc/ssh/sshd_config
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication no/' /etc/ssh/sshd_config
sudo service ssh restart

## Por qué
- Deshabilitar root evita ataques directos contra la cuenta más poderosa.
- Forzar autenticación por clave elimina ataques de diccionario.

## Diferencia antes / después
Antes: root podía loguearse y se podían probar contraseñas débiles.
Después: solo login con clave, root prohibido.

## Resultado esperado
Ataques de diccionario fallan.
