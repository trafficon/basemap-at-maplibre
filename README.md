# basemap.at MapLibre GL JS Example

This example shows how to use the [basemap.at](https://basemap.at/) Vector Map
with [MapLibre GL JS](https://github.com/maplibre/maplibre-gl-js).

## How to use basemap.at Vector styles with MapLibre GL JS

> [!CAUTION]
> As of 2024-10-13 the currently distributed [Source JSON](https://mapsneu.wien.gv.at/basemapv/bmapv/3857/) uses a relative path for `tiles`. This is not supported by the [TileJSON spec](https://github.com/mapbox/tilejson-spec/tree/master/3.0.0#32-tiles). For a current working example see [index.html](index.html) which uses a tempered [Style JSON](basemapvectorneu-root.json) pointing to a tempered [tile source JSON](basemapv-bmapv-3857.json).

### Should work, once official JSONs are fixed

```html
<script src="https://unpkg.com/maplibre-gl@4.7.1/dist/maplibre-gl.js"></script>
<link href="https://unpkg.com/maplibre-gl@4.7.1/dist/maplibre-gl.css" rel="stylesheet" />
<style>
  #map {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 100%;
  }
</style>

<script>
  var map = new maplibregl.Map({
    container: 'map',
    style: 'https://mapsneu.wien.gv.at/basemapvectorneu/root.json',
    bounds: [8.8587, 45.7823, 17.1608, 49.5752],
    fitBoundsOptions: { padding: 200 },
    attributionControl: false,
  });

  map.addControl(
    new maplibregl.AttributionControl({
      customAttribution: 'Quelle: <a href="https://basemap.at/" target="_blank" rel="noopener">basemap.at</a>',
    }),
  );
</script>
```

## Attribution

- [basemap.at](https://basemap.at/) Tiles [are released](https://basemap.at/#lizenz) under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
