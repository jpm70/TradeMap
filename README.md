# 📍 TradeMap

Buscador de negocios por actividad sobre un mapa: elige una ciudad (o usa tu ubicación) y mira restaurantes, cafeterías, farmacias, supermercados o bares en un radio de 3 km, con enlace «Cómo llegar».

**▶ En vivo:** https://jpm70.github.io/TradeMap/

Parte del proyecto [Un Fantasma en el Sistema](https://www.unfantasmaenelsistema.com).

## Cómo funciona
- **Ciudad:** autocompletado con [Photon](https://photon.komoot.io) (OpenStreetMap), sesgado hacia España para que «Alicante» sea la de Alicante y no la de Filipinas. Si escribes una ciudad sin elegir de la lista, se usa el primer resultado.
- **Negocios:** consulta a la API [Overpass](https://overpass-api.de) con las etiquetas de OpenStreetMap (`amenity=restaurant`, `shop=supermarket`…). Si un servidor no responde, prueba con dos espejos antes de rendirse.
- **Mapa:** [Leaflet](https://leafletjs.com) con teselas de CARTO (oscuro) y OpenStreetMap (claro).

Sin servidor, sin registro y sin API key.

## Limitaciones
- Los datos son los de OpenStreetMap: pueden faltar negocios o estar desactualizados, y no hay horarios ni valoraciones.
- Overpass es un servicio público y a veces va saturado; si falla, la página avisa y basta con reintentar.
- Radio fijo de 3 km.
- «Mi ubicación» pide permiso al navegador.

## Desarrollo local
Es un único `index.html` estático:

```bash
python -m http.server 8000
```

## Créditos
© colaboradores de [OpenStreetMap](https://www.openstreetmap.org/copyright), © CARTO. Proyecto educativo y sin ánimo de lucro.
