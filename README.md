# basemap.at MapLibre GL JS Example

This example shows how to use the [basemap.at](https://basemap.at/) Vector Map
with [MapLibre GL JS](https://github.com/maplibre/maplibre-gl-js).

## How to use basemap.at Vector styles with MapLibre GL JS

> **Warning**
> As of 2022-11-10 the currently distributed [Style JSON](https://maps.wien.gv.at/basemapv/bmapv/3857/resources/styles/root.json) uses relative paths. This is not supported by MapLibre (or the spec). For a current working example see [index.html](index.html) which uses a tempered [Style JSON](basemapv-bmapv-3857-resources-styles-root.json).

```html
<script src="https://unpkg.com/maplibre-gl@2.4.0/dist/maplibre-gl.js"></script>
<link href="https://unpkg.com/maplibre-gl@2.4.0/dist/maplibre-gl.css" rel="stylesheet" />
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
    style: 'https://maps.wien.gv.at/basemapv/bmapv/3857/resources/styles/root.json',
    center: [13.00975, 47.6964],
    zoom: 7,
    maxZoom: 17,
  });

  map.addControl(
    new maplibregl.AttributionControl({
      customAttribution: 'Quelle: <a href="https://basemap.at/" target="_blank" rel="noopener">basemap.at</a>',
    }),
  );
</script>
```

## Attribution

- [basemap.at](https://basemap.at/) Tiles [are released](https://basemap.at/#lizenz)
  under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
