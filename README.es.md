[English](README.md) · **Castellano** · [Euskara](README.eu.md)

# RedPi Tools

Conjunto de herramientas de auditoría de seguridad en Python, hecho a medida para
el proyecto **RedPi** — una red empresarial simulada (LAN / DMZ / WAN) usada para
aprender y demostrar seguridad de redes. Las herramientas se manejan por menú y se
dividen en defensivas y ofensivas.

> ⚠️ **Uso educativo / autorizado únicamente.** Estas herramientas se escribieron
> para un laboratorio propio y aislado, como parte de un proyecto de ciberseguridad
> de formación profesional. Úsalas solo contra sistemas de tu propiedad o para los
> que tengas permiso explícito por escrito. Ejecutarlas contra sistemas que no
> controlas puede ser ilegal.

Parte del [proyecto RedPi](https://iraitzaristi.github.io) · allí está el writeup
y la documentación completa.

## Herramientas

**Defensivas** (`defentsa/`)
- `mysql_kudeaketa.py` — interfaz de gestión de la base de datos MySQL.
- `pasahitz_analizatzailea.py` — analizador de robustez de las contraseñas almacenadas.
- `pasahitz_generadorea.py` — generador de contraseñas fuertes (hashea la salida con SHA-256).

**Ofensivas** (`erasoa/`)
- `sareko_eskanerra.py` — escáner de red, puertos y servicios.
- `web_analisia.py` — fuzzer de rutas web.
- `sniffer.py` — sniffer de tráfico HTTP/FTP.
- `arp_spoofer.py` — ARP spoofer (MITM).
- `xmlrpc.py` — fuerza bruta de credenciales al XML-RPC de WordPress.

`menu_nagusia.py` es el punto de entrada que une los dos menús.

## Requisitos

- Python 3
- `nmap` instalado en el sistema (lo usa el escáner)
- Paquetes de Python:

```bash
pip install -r requirements.txt
```

Algunas herramientas ofensivas (sniffer, ARP spoofer, escáner) capturan o
construyen paquetes en crudo y necesitan ejecutarse con privilegios de root (`sudo`).

## Uso

```bash
python3 menu_nagusia.py
```

## Configuración

Las herramientas se configuraron para el laboratorio RedPi, así que algunos scripts
contienen **valores del laboratorio fijados en el código** (IPs objetivo como
`172.16.1.10` y credenciales de prueba de la base de datos `technova_db`). Son
valores desechables de un entorno simulado y aislado — ajusta las IPs, los objetivos
y las credenciales al principio de cada script para tu propio entorno autorizado.

## Notas

- La interfaz y los comentarios del código están en **euskera**.
- `reverse_shellPHP.txt` es un payload estándar de reverse shell en PHP usado en el
  caso práctico del proyecto; incluido por completitud.

## Licencia

MIT — ver `LICENSE`.
