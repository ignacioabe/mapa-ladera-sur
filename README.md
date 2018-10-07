**La idea es hacer un mapa simple para ladera sur, pero siempre aparecen pequeños obstáculos.**

En principio, me basé en siguiente [ejemplo de hacer marcadores personalizados](https://www.mapbox.com/mapbox-gl-js/example/custom-marker-icons/)

Y también en esta [guía](https://www.mapbox.com/help/building-a-store-locator/), que contiene la mayoría de los pasos que necesito, excepto 

Para fuentes pesadas, mapbox [recomienda](https://www.mapbox.com/help/working-with-large-geojson-data/) meter el geojson en un archivo externo. Esto se hace del siguiente modo:

```
map.addSource('some id', {
  type: 'geojson',
  data: 'https://mydomain.mydata.geojson'
});
```

No es mi caso, me conviene meter el archivo en una variable. Lo único complejo sería aplicar eso a un sitio web de terceros, en el que uno no controla el HTML final.

---

Le agregué los controles básicos de navegación que había puesto en la primera prueba, y una función para encuadrar los marcadores independiente de la resolución, con `fitBounds`.