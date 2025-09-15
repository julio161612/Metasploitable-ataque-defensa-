# 8. SSH (puerto 22)

## Comando
# Fuerza bruta (laboratorio)
# hydra -L users.txt -P passwords.txt ssh://192.168.10.10

## Por qué
Detecta contraseñas débiles o root habilitado.

## Antes / Después
- Antes: root accesible con contraseña débil.  
- Después: root deshabilitado y solo login con clave.

## Resultado esperado
- Credenciales válidas encontradas (solo en laboratorio).
