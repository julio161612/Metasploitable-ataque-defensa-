# 10. Samba (puertos 139/445)

## Comando
# Recon
# enum4linux -a 192.168.10.10 | tee RED_TEAM/outputs/red_samba_enum.txt

## Por qué
Detecta shares públicos o inseguros.

## Antes / Después
- Antes: shares públicos con lectura/escritura.  
- Después: shares autenticados y restringidos.

## Resultado esperado
- RED_TEAM/outputs/red_samba_enum.txt con shares listados.
