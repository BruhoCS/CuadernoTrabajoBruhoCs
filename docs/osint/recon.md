# Reconocimiento general

Suites que automatizan la recopilación de información OSINT a partir de un dominio, correo, IP o nombre.

---

## theHarvester

> **Tipo:** CLI · **Estado:** ✅ Usada (UD1-3, Ejercicio OSINT)

Herramienta de reconocimiento **pasivo**. De un dominio saca **correos, subdominios, IPs, hosts y nombres de usuario** consultando buscadores y fuentes públicas (Google, Bing, DuckDuckGo, Hunter.io, crt.sh, Shodan…). Viene de serie en Kali.

**Uso básico**

```bash
theHarvester -d dominio.com -b all -l 500
```

- `-d` → dominio objetivo.
- `-b` → fuentes (`all`, o `bing,duckduckgo,crtsh,hunter,…`).
- `-l` → límite de resultados por fuente.
- `-f salida` → guarda en `salida.json` / `.xml`.

**APIs**: muchas fuentes (Hunter, Bing, Shodan…) necesitan clave en `~/.theHarvester/api-keys.yaml`. Sin clave se saltan y se ven avisos `[!] Missing API key` (no es error).

!!! tip "Correos"
    Las fuentes gratuitas sacan bien **subdominios**, pero para **correos** la que de verdad funciona es **Hunter.io** (hay que configurar su API key).

---

## SpiderFoot

> **Tipo:** Web / CLI · **Estado:** ✅ Usada (Ejercicio OSINT)

Escáner OSINT automatizado que consulta **más de 1.000 fuentes**. Puede empezar desde dominio, IP, subred, ASN, **correo, teléfono o nombre de persona**. Incluido en Kali.

**Arrancar la interfaz web**

```bash
spiderfoot -l 127.0.0.1:5001
```

Abrir `http://127.0.0.1:5001` → **New Scan** → nombre + objetivo (detecta el tipo solo) → modo (`Passive`, `Investigate`, `Footprint`) → **Run Scan Now**.

**Dónde mirar los resultados**: pestaña **Browse** → categorías como *Human Name*, *Email Address*, *Accounts on External Sites*, *Usernames*.

!!! warning
    Muchos módulos necesitan API key; sin ellas saldrán muchos *Errors* y pocos resultados. Es normal.

---

## Maltego

> **Tipo:** GUI · **Estado:** ⬜ Por probar

Una de las herramientas más potentes para **minería de datos y grafos de relaciones** de una organización. En Kali viene **Maltego CE** (versión libre, limitada). Usa **transformadas** (scripts que automatizan consultas, p. ej. con la API de VirusTotal para subdominios) y muestra los resultados en **árbol/grafo**.

Útil para el informe OSINT con **grafo de vínculos** (dominios → IPs → correos → personas → documentos).

---

## recon-ng

> **Tipo:** CLI · **Estado:** ⬜ Por probar

Framework de reconocimiento con estructura tipo Metasploit (módulos, workspaces). Automatiza recolección y la guarda en una base de datos. Incluido en Kali.

```bash
recon-ng
[recon-ng] > marketplace install all
[recon-ng] > modules load recon/domains-hosts/hackertarget
```

---

## OSINT Framework

> **Tipo:** Web · **Estado:** ⬜ Por probar

No es una herramienta, sino un **directorio** (osintframework.com) que clasifica cientos de recursos OSINT por tipo de dato (usuario, correo, dominio, IP, imágenes…). Útil como punto de partida para saber **qué** herramienta usar.
