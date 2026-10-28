# Metadatos

Extraer información "oculta" de documentos (autor, usuario, software, fechas, GPS…).

---

## exiftool

> **Tipo:** CLI · **Estado:** ✅ Usada (UD1-4, Ejercicio OSINT)

El estándar para **leer, borrar y modificar** metadatos de casi cualquier formato. Viene en Kali.

```bash
exiftool imagen.jpg                 # ver todo
exiftool -r carpeta/                # recursivo sobre una carpeta
exiftool -r -Creator -Producer -Author -"Last Modified By" carpeta/
```

**Campos útiles**: `Producer`/`Creator`/`Software` → programa usado; `Author`/`Last Modified By` → usuarios; `GPS*` → coordenadas; `Copyright` → a veces un handle.

**Agrupar software** (para tabla):

```bash
exiftool -r -T -Creator -Producer carpeta/ | sort | uniq -c | sort -rn
```

**Buscar correos en los metadatos**:

```bash
exiftool -r carpeta/ | grep -iE "[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}"
```

---

## MetaDetective

> **Tipo:** CLI · **Estado:** ✅ Usada (UD1-4)

Scrapea documentos de una web, los **descarga** y extrae metadatos (usa exiftool por debajo). Alternativa que **sí funciona** cuando Metagoofil/Maltego no scrapean.

```bash
# Contar documentos disponibles
python3 MetaDetective.py --scraping --scan --url https://web.com/ --extensions pdf doc docx odt
# Descargar a una carpeta
python3 MetaDetective.py --scraping --url https://web.com/ --download-dir ./docs --extensions pdf doc docx --depth 1
# Analizar y resumir (software/usuarios/correos)
python3 MetaDetective.py -d ./docs --summary
```

---

## FOCA

> **Tipo:** GUI (Windows) · **Estado:** ⬜ Por probar

Analiza una web completa: descarga documentos y clasifica los metadatos en pestañas (**Users, Software, Emails, Operating Systems, Servers**). Es de **Windows** → usar en la VM de Windows.

---

## Metagoofil

> **Tipo:** CLI · **Estado:** ⬜ (no funciona para scrapear)

Descargaba documentos de una web y extraía metadatos, pero **Google tiene capado el scraping**, así que ya no tira bien. Usar **MetaDetective** o **FOCA** en su lugar.

---

## MetaFinder / MetaData2Go

> **Tipo:** CLI / Web · **Estado:** ⬜ Por probar

- **MetaFinder**: alternativa a FOCA en Linux; busca documentos en buscadores y extrae metadatos.
- **MetaData2Go** ([metadata2go.com](https://www.metadata2go.com)): lectura de metadatos online, sin instalar.
