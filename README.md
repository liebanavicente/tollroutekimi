# TollRoute

Calcula la ruta más rápida en coche respetando tu presupuesto máximo de peajes en España.

🔗 **Demo en vivo:** [https://tollroutekimi.vercel.app](https://tollroutekimi.vercel.app)

## Características

- 🗺️ **Mapa interactivo** con Leaflet + OpenStreetMap
- 💰 **Cálculo de peajes reales** con datos de 667 segmentos de autopistas españolas
- 🎚️ **Slider de presupuesto** para ajustar el máximo en peajes
- ⚡ **Comparación de rutas**: más rápida vs. sin peajes
- 📱 **Diseño responsive** optimizado para móvil
- 🔄 **Geocodificación en segundo plano** de estaciones de peaje (con cache local)

## Datos

- **667 segmentos de peaje** extraídos de fuentes oficiales
- **11 autopistas** cubiertas:
  - SEITT: R-2, R-3, R-4, R-5, M-12, AP-36, AP-41, AP-7 Cartagena-Vera
  - Acega: AP-53
  - Audasa: AP-9
  - Autoestradas de Galicia: AG-55, AG-57
- **Actualizado:** septiembre 2026

## Stack

| Servicio | Uso |
|----------|-----|
| Leaflet | Mapas (gratuito) |
| OpenStreetMap | Tiles de mapa (gratuito) |
| OSRM | Routing / cálculo de rutas (gratuito) |
| Nominatim | Geocodificación de direcciones (gratuito) |
| Datos propios | Scraping automatizado de tarifas oficiales |

## Uso local

```bash
# Clonar el repositorio
git clone https://github.com/liebanavicente/tollroutekimi.git
cd tollroutekimi

# Abrir en el navegador (no requiere servidor)
open index.html
```

## Deploy en Vercel

### Opción A: CLI de Vercel

```bash
# Instalar Vercel CLI
npm i -g vercel

# Login y deploy
vercel login
vercel --prod
```

### Opción B: Dashboard web

1. Ve a [vercel.com/new](https://vercel.com/new)
2. Importa el repositorio `liebanavicente/tollroutekimi`
3. Framework preset: **Other** (HTML estático)
4. Click en **Deploy**

## Scrapers incluidos

- `scraper_acega.py` — AP-53 (HTML tabular)
- `scraper_seitt.py` — 8 autopistas (PDFs oficiales)
- `scraper_abertis.py` — AP-6, AP-68, AP-71 (PDFs matriz OD)

## Notas técnicas

- La app es **100% estática** (HTML + JS + CSS). No requiere backend.
- Los datos de peajes se cargan desde `spain_tolls.json`.
- Las coordenadas de estaciones de peaje se geocodifican bajo demanda con Nominatim y se cachean en `localStorage`.
- Para rutas donde no hay datos de peajes disponibles, se usa una estimación heurística (~0.10€/km en autopistas de peaje).

## Licencia

MIT
