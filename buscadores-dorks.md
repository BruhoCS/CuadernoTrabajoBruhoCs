# Buscadores y dorks

Sacar información usando buscadores web y buscadores tecnológicos.

---

## Google dorks

> **Tipo:** Web · **Estado:** ✅ Usados (UD1-2, UD1-3)

Operadores avanzados de Google para búsquedas dirigidas. La [Google Hacking Database](https://www.exploit-db.com/google-hacking-database) tiene miles.

| Operador | Qué hace |
|---|---|
| `" "` | Búsqueda exacta |
| `-palabra` | Excluye una palabra |
| `site:` | Solo en ese sitio |
| `filetype:` / `ext:` | Archivos de ese tipo |
| `inurl:` | La palabra en la URL |
| `intitle:` | La palabra en el título |
| `cache:` | Versión en caché |
| `OR` / `AND` | Lógica |

**Ejemplos usados**

```text
site:cifprodolfoucha.es filetype:pdf
site:dominio.gal filetype:doc OR filetype:docx OR filetype:odt
inurl:robots.txt filetype:txt
"@dominio.com" password
"correo@dominio.com" site:pastebin.com
```

!!! tip
    `robots.txt` (`inurl:robots.txt`) a menudo delata rutas y paneles que la organización no quiere indexar.

---

## Bing

> **Tipo:** Web · **Estado:** ⬜ Por probar (como complemento)

Comparte muchos operadores con Google, pero añade:

- `ip:` → búsqueda inversa (dominios/subdominios alojados en una IP).
- `domain:` → en vez de `site:`.

A veces da resultados que Google no muestra; conviene comparar entre buscadores.

---

## Shodan

> **Tipo:** Web · **Estado:** ✅ Usada (UD1-2)

Buscador **tecnológico**: indexa los **banners** de servidores y dispositivos conectados a Internet (routers, webcams, IoT, bases de datos…). Detecta servicios, puertos y versiones, y sugiere vulnerabilidades. Es **escaneo pasivo** (el objetivo no se entera). Requiere registro; el plan gratis está muy limitado.

**Operadores gratuitos**: `country:`, `port:`, `product:`.
**Solo de pago/miembros**: `city:`, `os:`, `version:`, `vuln:`.

**Ejemplos**

```text
product:MySQL country:ES
port:2375                 (Docker expuesto)
"authentication disabled" VNC
```

Alternativas: **Censys**, ZoomEye, FOFA, Criminal IP.

---

## Censys

> **Tipo:** Web · **Estado:** ⬜ Por probar

Similar a Shodan: escanea Internet e indexa hosts, certificados y servicios. Muy bueno para **certificados TLS** (sirve para descubrir subdominios). Plan gratis con cuota de consultas.
