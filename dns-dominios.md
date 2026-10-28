# DNS y dominios

Averiguar IPs, servidores de correo, servidores DNS y subdominios de un dominio.

---

## whois

> **Tipo:** CLI/Web · **Estado:** ⬜ Por probar

Consulta los datos de registro de un dominio (registrador, fechas, a veces correo/nombre de contacto).

```bash
whois dominio.com
```

---

## nslookup

> **Tipo:** CLI · **Estado:** ✅ Usada (UD1-3)

Consultas DNS básicas.

```bash
nslookup dominio.com                 # IP (registro A)
nslookup -type=mx dominio.com        # servidores de correo
nslookup -type=ns dominio.com        # servidores DNS con autoridad
```

Alternativa online: Robtex.

---

## dig

> **Tipo:** CLI · **Estado:** ✅ Usada (UD1-3)

Más potente que nslookup.

```bash
dig +short -t NS dominio.com                      # servidores DNS
dig +short -t MX dominio.com                      # correo
dig +short -t AXFR dominio.com @ns1.servidor.com  # intento de transferencia de zona
```

!!! note "Transferencia de zona (AXFR)"
    Un servidor bien configurado responde **`Transfer failed`**. Si deja transferir, revela todos los subdominios → mala configuración.

---

## host

> **Tipo:** CLI · **Estado:** ✅ Usada (fuerza bruta de subdominios)

```bash
host subdominio.dominio.com
```

**Script de fuerza bruta** con diccionario:

```bash
#!/bin/bash
for nombre in $(cat diccionario-dns.txt); do
    host $nombre.dominio.com | grep "has address"
done
```

Diccionarios: **SecLists** (`Discovery/DNS`), dnspop (bitquark).

---

## dnsenum / dnsrecon

> **Tipo:** CLI · **Estado:** ⬜ Por probar

Automatizan todo lo anterior (registros, fuerza bruta de subdominios, transferencia de zona). Vienen en Kali.

```bash
dnsenum dominio.com
dnsrecon -d dominio.com
```

---

## sublist3r / amass

> **Tipo:** CLI · **Estado:** ⬜ Por probar

Enumeración **potente de subdominios** desde múltiples fuentes. Son la respuesta al comentario del profe de "faltan subdominios por encontrar".

```bash
sublist3r -d dominio.com
amass enum -d dominio.com
```

---

## dnsdumpster

> **Tipo:** Web · **Estado:** ✅ Usada (UD1-3)

[dnsdumpster.com](https://dnsdumpster.com) — muy gráfico. De un dominio saca subdominios, IPs, registros, hosting y servicios (banners). Buena alternativa visual a dnsenum.

---

## crt.sh

> **Tipo:** Web · **Estado:** ⬜ Por probar

[crt.sh](https://crt.sh) — busca en los **logs de Certificate Transparency**. Al pedir `%.dominio.com` salen subdominios que aparecieron en certificados TLS (muchos que la fuerza bruta no encuentra).
