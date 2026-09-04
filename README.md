# TollRoute

Calcula la ruta mas rapida en coche respetando tu presupuesto maximo de peajes.

## Demo

[https://tollroutekimi.vercel.app](https://tollroutekimi.vercel.app) *(tras deploy)*

## Datos

- **667 segmentos de peaje** extraidos automaticamente de fuentes oficiales
- **11 autopistas** cubiertas: SEITT (R-2, R-3, R-4, R-5, M-12, AP-36, AP-41, AP-7 Cartagena-Vera), Acega (AP-53), Audasa (AP-9), Autoestradas de Galicia (AG-55, AG-57)
- **Actualizado:** septiembre 2026

## Stack

- Leaflet + OpenStreetMap (mapas 0€)
- OSRM (routing 0€)
- Nominatim (geocodificacion 0€)
- Datos de peajes propios (scraping automatico)

## Uso local

Abre `index.html` en cualquier navegador. No requiere servidor.

## Deploy en Vercel

```bash
# 1. Subir a GitHub
git remote add origin https://github.com/TU_USUARIO/tollroutekimi.git
git branch -m main
git push -u origin main

# 2. Importar en Vercel
# ve a https://vercel.com/new → importa el repo
# Framework preset: Other (HTML estatico)
```

## Scrapers incluidos

- `scraper_acega.py` — AP-53 (HTML tabular)
- `scraper_seitt.py` — 8 autopistas (PDFs oficiales)
- `scraper_abertis.py` — AP-6, AP-68, AP-71 (PDFs matriz OD)
