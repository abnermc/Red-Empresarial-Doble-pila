# Red-Empresarial-Doble-pila
 Red LAN empresarial dual-stack IPv4/IPv6 con VLSM, enrutamiento estático y túnel IPv6/IPv4 — Cisco Packet Tracer
# Red LAN Empresarial con Doble Pila IPv4/IPv6
**Curso:** Redes 1 — Universidad Privada del Norte (Trujillo, 2026)  
**Herramienta:** Cisco Packet Tracer 9.x  
**Empresa simulada:** Seguros Andina Corredores de Seguros S.A.C.

## Descripción
Diseño e implementación completa de una red LAN empresarial con doble pila 
IPv4/IPv6, incluyendo:
- Subnetting jerárquico con VLSM sobre 172.16.5.0/23
- Enrutamiento estático IPv4 e IPv6 en 3 routers Cisco 2911
- Túnel IPv6 sobre IPv4 (mode ipv6ip) entre R2 y R3
- Servicios de red: DHCP con relay, DNS (A/AAAA), HTTP, SMTP/POP3, FTP/TFTP
- Verificación de conectividad: ping, tracert, nslookup, acceso HTTP y correo

## Topología
![Topología](capturas/topologia.png)

## Direccionamiento IPv4 (VLSM)
| Segmento | Red | Máscara | Gateway |
|---|---|---|---|
| S1 — Comercial (130 hosts) | 172.16.5.0 | /24 | 172.16.5.1 |
| S5 — Administración (40 hosts) | 172.16.6.0 | /26 | 172.16.6.1 |
| S2 — Servidores IPv4 (12 hosts) | 172.16.6.64 | /28 | 172.16.6.65 |
| Enlace R1–R2 | 172.16.6.80 | /30 | — |
| Enlace R2–R3 | 172.16.6.84 | /30 | — |

## Servicios implementados
| Servidor | IP | Servicio |
|---|---|---|
| ServerHTTPv4 | 172.16.6.66 | HTTP — segurosandina.pe |
| ServerDHCP | 172.16.6.67 | DHCP (pools S1 y S5) |
| ServerDNS | 172.16.6.68 | DNS IPv4 (registro A) |
| ServerHTTPv6 | 2001:db8:acad:6::2 | HTTP IPv6 |
| ServerDNSv6 | 2001:db8:acad:6::3 | DNS IPv6 (registro AAAA) |
| ServerSMTPv6 | 2001:db8:acad:6::4 | Correo SMTP/POP3 |

## Archivos
- `Red Empresarial` — archivo .pkt de Cisco Packet Tracer
 - `Informe del caso` — informe técnico completo en PDF
- `capturas/` — evidencia fotográfica de pruebas de conectividad
