# Comandos y dorks

Chuletario de lo usado en los ejercicios, para copiar y pegar.

## DNS y dominios

```bash
# IP, correo y DNS
nslookup dominio.com
nslookup -type=mx dominio.com
nslookup -type=ns dominio.com

# dig
dig +short -t NS dominio.com
dig +short -t MX dominio.com
dig +short -t AXFR dominio.com @ns1.servidor.com     # transferencia de zona

# Fuerza bruta de subdominios
for n in $(cat diccionario-dns.txt); do host $n.dominio.com | grep "has address"; done
```

## theHarvester

```bash
theHarvester -d dominio.com -b all -l 500
theHarvester -d dominio.com -b hunter -l 500          # solo Hunter (correos)
# API keys en: ~/.theHarvester/api-keys.yaml  (sección hunter)
```

## h8mail

```bash
h8mail --gen-config
h8mail -t correos.txt -c h8mail_config.ini
```

## Descargar documentos de una web (metadatos)

```bash
# MetaDetective
python3 MetaDetective.py --scraping --scan --url https://web.com/ --extensions pdf doc docx odt
python3 MetaDetective.py --scraping --url https://web.com/ --download-dir ./docs --extensions pdf doc docx --depth 1

# wget (alternativa)
wget -r -l5 -nd -e robots=off --wait=1 -A pdf,doc,docx,odt,xls,xlsx,ppt,pptx -P ./docs https://web.com/
```

## exiftool

```bash
exiftool -r ./docs/
exiftool -r -T -Creator -Producer ./docs/ | sort | uniq -c | sort -rn
exiftool -r ./docs/ | grep -iE "[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}"
```

## SpiderFoot

```bash
spiderfoot -l 127.0.0.1:5001     # luego abrir http://127.0.0.1:5001
```

## Google dorks

```text
site:dominio.com filetype:pdf
site:dominio.com filetype:doc OR filetype:docx OR filetype:odt
inurl:robots.txt filetype:txt
"@dominio.com" password
"correo@dominio.com" site:pastebin.com
```

## Shodan

```text
product:MySQL country:ES
port:2375
"authentication disabled" VNC
```
