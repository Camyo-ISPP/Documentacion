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
| Pedro Jiménez Guerrero | Estudio previo, estructura general y análisis de 6 opciones. |

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


## Conclusión
