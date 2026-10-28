# Cuaderno de Trabajo

Notas, comandos, dorks y herramientas que voy usando en el curso de especialización en **Ciberseguridad en entornos de las TI** (CIFP Rodolfo Ucha Piñeiro, 2026/2027).

Formato inspirado en los cuadernos tipo *OSCP notes*: cada herramienta con qué es, cómo se instala y cómo se usa, para tenerlo a mano en exámenes, prácticas y CTFs.

## Cómo está organizado

De momento el Tema 1 de Hacking Ético es **OSINT**, así que el grueso son herramientas de recopilación de información, separadas por categoría:

- **[Reconocimiento general](osint/recon.md)** — suites que automatizan OSINT.
- **[Buscadores y dorks](osint/buscadores-dorks.md)** — Google/Bing, Shodan, Censys.
- **[DNS y dominios](osint/dns-dominios.md)** — IPs, subdominios, registros.
- **[Correos, usuarios y personas](osint/correos-personas.md)** — de un email/username a sus cuentas.
- **[Fugas y contraseñas](osint/fugas-passwords.md)** — comprobar brechas y credenciales filtradas.
- **[Metadatos](osint/metadatos.md)** — extraer info oculta de documentos.
- **[Comandos y dorks](comandos.md)** — chuletario de lo usado en los ejercicios.

## Leyenda

En cada herramienta uso estas etiquetas:

- **Estado** — ✅ Usada en un ejercicio · ⬜ Por probar (está en los apuntes pero aún no la usé).
- **Tipo** — `CLI` (terminal) · `Web` (navegador) · `GUI` (app de escritorio).

!!! note "Nota"
    Este cuaderno es un documento vivo: lo iré ampliando con cada tema (Web, redes, bastionado, forense…).

## Resumen rápido de herramientas

| Herramienta | Categoría | Tipo | Estado |
|---|---|---|---|
| theHarvester | Correos/dominios | CLI | ✅ |
| SpiderFoot | Reconocimiento | Web/CLI | ✅ |
| exiftool | Metadatos | CLI | ✅ |
| MetaDetective | Metadatos | CLI | ✅ |
| nslookup / dig / host | DNS | CLI | ✅ |
| dnsdumpster | DNS | Web | ✅ |
| Google dorks | Buscadores | Web | ✅ |
| Shodan | Buscadores | Web | ✅ |
| Have I Been Pwned | Fugas | Web | ✅ |
| LeakCheck | Fugas | Web | ✅ |
| DeHashed | Fugas | Web | ✅ |
| Intelligence X | Fugas | Web | ✅ |
| h8mail | Fugas | CLI | ✅ |
| Hunter.io | Correos | Web/API | ✅ |
| Fingerprint.to | Personas | Web | ✅ |
| Maltego | Reconocimiento | GUI | ⬜ |
| FOCA | Metadatos | GUI | ⬜ |
| WhatsMyName / Sherlock / Maigret | Usuarios | CLI/Web | ⬜ |
| Holehe / GHunt / Epieos | Correos | CLI/Web | ⬜ |
| amass / sublist3r / dnsenum | DNS | CLI | ⬜ |
| Censys | Buscadores | Web | ⬜ |
