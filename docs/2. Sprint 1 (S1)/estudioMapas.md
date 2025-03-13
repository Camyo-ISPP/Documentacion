<h1 align="center">
  Camyo
</h1>

<p align="center">
  <img src="https://i.imgur.com/C72nY4p.png" alt="Logo de Camyo" width="150">
</p>

<h3 align="center">
  <strong>Grupo 5</strong>
</h3>

<h1 align="center">
  <strong>Estudio APIs de Mapas</strong>
</h1>

<p align="center">
  <strong>Nombre del Entregable:</strong> Sprint 1
</p>
<p align="center">
  <strong>Asignatura:</strong> Ingeniería del Software y Práctica Profesional  
</p>
<p align="center">
  <strong>Curso:</strong> 2024-2025  
</p>

### Contribuciones del Equipo


| Nombre(s) y Apellido(s) | Tipo de Contribución                             |
| ------------------------- | --------------------------------------------------- |
| Pedro Jiménez Guerrero | Estudio previo, estructura general y análisis |

## Tabla de Contenidos

- [Tabla de Contenidos](#tabla-de-contenidos)
- [Introducción](#introducción)
- [Opciones Open-Source](#opciones-open-source)
  - [MapLibre](#maplibre)
  - [Leaflet](#leaflet)
  - [OpenLayers](#openlayers)
- [Opciones de proveedores privados](#opciones-de-proveedores-privados)
  - [TomTom](#tomtom)
  - [Apple Maps](#apple-maps)
  - [MapBox](#mapbox)
- [Posibles implementaciones](#posibles-implementaciones)
- [Conclusión](#conclusión)


## Introducción

En este documento se estudian y contrastan distintas opciones para implementar una API de mapas en la aplicación, tanto privadas como open-source.

El objetivo es contar con una funcionalidad que muestre a los usuarios un mapa con posibilidad de crear rutas adecuadas a sus necesidades, puediendo ver qué áreas de descanso y gasolineras hay en el camino.

## Opciones Open-Source

### [MapLibre](https://maplibre.org/)
| Mapa | Lugares de Interés | Rutas  |
| :-----: | :--------------------: | :--------: |
| ✅   | ❌    | Plugin |
**Pros**:
- Permite personalizar la apariencia del mapa.
- Se puede implementar las rutas se por un plugin comunitario.

**Cons**:
- No cuenta con puntos de interés
- Las implementaciones son en Typescript para web y C++ para Android, lenguajes que no usamos.

### [Leaflet](https://leafletjs.com/)
| Mapa | Lugares de Interés | Rutas  |
| :-----: | :--------------------: | :--------: |
| ✅   | ✅    | Plugin |

**Pros**:
- Implementación sencilla en JS
- Muchos tutoriales
- Tiene puntos de interés
- Rutas (aparentemente) fácilmente implementables mediante un plugin comunitario.

**Cons**:
- Usa OpenStreetMap, por lo que algunos datos pueden estar incompletos.

### [OpenLayers](https://openlayers.org/)

| Mapa | Lugares de Interés | Rutas  |
| :-----: | :--------------------: | :--------: |
| ✅   | ❌    | ❌ |

**Pros**:
- Tiene mapa.

**Cons**:
- Le falta todo lo demás.

## Opciones de proveedores privados

### [TomTom](https://developer.tomtom.com/)

| Mapa | Lugares de Interés | Rutas  |
| :-----: | :--------------------: | :--------: |
| ✅   | ✅    | ✅ |

**Pros:**
- Gran cantidad de APIs [muy diversas](https://developer.tomtom.com/api-explorer-index/documentation/product-information/introduction).
- La API de rutas tiene muchos parámetros y es muy personalizable, entre otras cosas pudiendo elegir "camión" como vehículo.
- Se usar de forma comercial.
- Precios económicos y suscripción Freemium bastante generosa.

**Cons**:
- Es necesario generar una API key para usarla.

### [Apple Maps](https://developer.apple.com/maps/)

| Mapa | Lugares de Interés | Rutas  |
| :-----: | :--------------------: | :--------: |
| ✅   | ✅    | ✅ |

**Pros:**
- API completa para lo que necesitamos.

**Cons**:
- Documentación confusa.
- Hace falta una API key para usarse, que se consigue iniciando sesión.
- No se sabe el pricing.

### [MapBox](https://www.mapbox.com/maps)

| Mapa | Lugares de Interés | Rutas  |
| :-----: | :--------------------: | :--------: |
| ✅   | ✅    | ✅ |

**Pros:**
- Mapbox Studio: se puede personalizar el mapa completamente para adaptarlo al estilo del proyecto.
- Permite mapas y rutas offline.
- Suscripción gratuita generosa.

**Cons**:
- Hay que resgistrarse para poder usarla.
- Una vez se pasan los límites de la versión gratuita, los precios escalan rápido.

## Posibles implementaciones
Se estudiarán las implementaciones de las opciones más interesantes: [Leaflet](#leaflet) y [TomTom](#tomtom).

### [Leaflet](https://leafletjs.com/examples/quick-start/)

Es una implementación sencilla, sólo hay que escribir unas líneas de código en el HTML de la página para incluirlo:
```html
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
    integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY="
    crossorigin=""/>

<!-- Make sure you put this AFTER Leaflet's CSS -->
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"
    integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo="
    crossorigin=""></script>
<style>
    #map {
      width: 100vw;
      height: 100vh;
    }
</style>
<div id="map"></div>
```

Una vez hecho eso, trabajando ahora en JS, se crea un mapa con unas coordenadas concretas gracias a las tiles proporcionadas por [OpenStreetMap](https://www.openstreetmap.org/):

```javascript
var map = L.map('map').setView([51.505, -0.09], 13);
L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
}).addTo(map);
```
Para el plugin de rutas, se sigue la siguiente [guía](https://www.liedman.net/leaflet-routing-machine/#getting-started). En dicha guía hay una nota indicando que depende del servidor demostración de OSRM que ya no es mantenido, por lo que habría que buscar otro proveedor. Una forma de superar este obstáculo es implementar una [extensión que soporte la API de enrutamiento de TomTom](https://github.com/mrohnstock/lrm-tomtom).

Un problema de esta solución es que mientras que los datos de OpenStreetMap son de uso libre, no lo son así su servidor de tiles, por lo que hay que investigar si nuestro uso de su servicio está contemplado en la [política de uso](https://operations.osmfoundation.org/policies/tiles/)



### [TomTom](https://developer.tomtom.com/documentation)
La empresa proporciona tanto un SDK para implementar mapas visualmente, como una enorme variedad de APIs.

La implementación del [SDK de mapas](https://developer.tomtom.com/maps-sdk-web-js/tutorials/basic/display-vector-map) es algo más larga que la de [leaflet](#leaflet-1):

1. Instalar la librería de mapas: `npm i @tomtom-international/web-sdk-maps`
1. Crear un documento HTML con el siguiente script: 
```html
<!DOCTYPE html>
<html class="use-all-space">
  <head>
    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />
    <meta charset="UTF-8" />
    <title>My Map</title>
    <meta
      name="viewport"
      content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no"
    />
    <!-- Replace version in the URL with desired library version -->
    <link
      rel="stylesheet"
      type="text/css"
      href="https://api.tomtom.com/maps-sdk-for-web/cdn/6.x/<version>/maps/maps.css"
    />
    <style>
      #map {
        width: 100vw;
        height: 100vh;
      }
    </style>
  </head>
  <body>
    <div id="map" class="map"></div>
    <!-- Replace version in the URL with desired library version -->
    <script src="https://api.tomtom.com/maps-sdk-for-web/cdn/6.x/<version>/maps/maps-web.min.js"></script>
    <script>
      tt.setProductInfo("<your-product-name>", "<your-product-version>")
      tt.map({
        key: "<your-tomtom-API-key>",
        container: "map",
      })
    </script>
  </body>
</html>
 ```

La [librería de APIs](https://developer.tomtom.com/api-explorer-index/documentation/product-information/introduction#api-explorer-page-links) es muy completa y proporciona URLs para tiles de mapas, rutas, puntos de interés, búsqueda, geocodificación... Un ejemplo es la siguiente ruta para obtener una tile de mapa rasterizada:
`https://{baseURL}/map/{versionNumber}/tile/{layer}/{style}/{zoom}/{X}/{Y}.{format}?key={Your_API_Key}&tileSize={tileSize}&view={geopoliticalView}&language={language}`

Hay que tener en cuenta el [pricing](https://developer.tomtom.com/pricing) del servicio, ya que cuanto más llamadas se hagan más aumentará el precio. Sin embargo, el tier "freemium" nos proporciona suficientes llamadas diarias para satisfacer a nuestros usuarios sin pasarnos de la cuota, ya que el volumen que manejamos ahora mismo no es muy elevado.



## Conclusión

La implementación de Leaflet es sencilla pero tiene deficiencias, como el uso no libre de las tiles de OSM o la dependencia del enrutado de un servidor que ya no es mantenido. Esto se complementa perfectamente con la API que ofrece TomTom, pudiendo usar su API de tiles, enrutado, o las que se crean necesarias.

Otra opción es implementar el SDK de mapas ofrecido por TomTom en vez de Leaflet, lo que eliminará la dependencia de plugins comunitarios.

El contenido de este documento se presentará al resto del grupo para llegar a un consenso a la hora de tomar la decisión final de qué método implementar. 