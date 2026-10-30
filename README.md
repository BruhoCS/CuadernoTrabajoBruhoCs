# Cuaderno de Trabajo — BruhoCS

Notas, comandos y herramientas del curso de especialización en **Ciberseguridad en entornos de las TI** (CIFP Rodolfo Ucha Piñeiro, 2026/2027).

## Ver la web

Una vez activado GitHub Pages, el cuaderno se publica en:

```
https://bruhocs.github.io/CuadernoTrabajoBruhoCs/
```

## Ejecutar en local

```bash
pip install -r requirements.txt
mkdocs serve
```

Abre http://127.0.0.1:8000

## Desplegar

El workflow `.github/workflows/deploy.yml` construye y publica el sitio en cada `push` a `main`.
Hay que activar Pages en **Settings → Pages → Source: GitHub Actions**.
