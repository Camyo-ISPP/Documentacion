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
  <strong>Investigación de Técnicas de SEO y Palabras Clave</strong>
</h1>

<p align="center">
  <strong>Nombre del Entregable:</strong> Preparing Project Launch
</p>
<p align="center">
  <strong>Asignatura:</strong> Ingeniería del Software y Práctica Profesional  
</p>
<p align="center">
  <strong>Curso:</strong> 2024-2025  
</p>

### Contribuciones del Equipo

| Nombre(s) y Apellido(s)          | Tipo de Contribución          |
|----------------------------------|-------------------------------|
| Diego José Pérez Vargas          | Redacción del Documento       |

## Tabla de Contenidos

1. [Introducción](#1-introducción)
2. [Prerrenderizado](#2-prerrenderizado)
3. [Enlazado interno](#3-enlazado-interno)
4. [Menos carga dinámica en los listados](#4-menos-carga-dinámica-en-listados)
5. [Añadir etiquetas](#5-añadir-etiquetas)

## 1. Introducción

La optimización de motores de búsqueda (*search engine optimisation* en inglés, de donde provienen las siglas **SEO**) consiste en una serie de técnicas y procesos que buscan aumentar el tráfico que recibe un sitio web por los motores de búsqueda, herramientas que devuelven enlaces relevantes según las búsquedas de los usuarios. Para Camyo, utilizar SEO es una buena manera de hacer que la aplicación pueda ser encontrada con más facilidad, al aumentar el puesto en el que aparece en los resultados de las búsquedas de usuarios potenciales.

Este documento tiene el fin de evaluar las distintas técnicas de SEO que podrían ser utilizadas en Camyo, cómo utilizarlas y las palabras clave que definen mejor a nuestra aplicación y que deberían devolver Camyo como resultado al buscarlas.

## 2. Prerrenderizado

Los motores de búsqueda más populares hacen uso de arañas web (*web crawler*) para encontrar sitios web. Las páginas encontradas mediante *crawling* son indizadas, para recopilar etiquetas y atributos como el idioma, la fecha de creación/actualización y la localización geográfica de la página.

Sin embargo, estas etiquetas y atributos no son suficientes para describir la finalidad de la página. Ya que Camyo usa React Native, los contenidos se renderizan en el cliente. Por tanto, los motores de búsqueda no pueden acceder a la mayoría de la información que se encuentra en estas páginas web, debido a que suelen leer solo o mayoritariamente el HTML.

Para solucionar este problema, existen soluciones de mercado que permiten prerrenderizar páginas y así optimizarlas para las arañas web. [Prerender.io](https://prerender.io/) es la herramienta más popular para el SEO de páginas web con JavaScript.

Sin embargo, no todas las páginas deberían ser accedidas por las arañas web (por ejemplo, paneles de admin o la interfaz de pago). Para estos casos, se debe añadir un archivo `robots.txt` en la raíz del sitio web, que permite establecer un listado de direcciones dentro del sitio web que los bots no tendrán permitido acceder. Más información acerca de este tipo de archivo está disponible en [robotstxt.org](https://www.robotstxt.org/robotstxt.html).

## 3. Enlazado interno

En Camyo, para pasar de una página a otra, se suelen usar botones que llaman a React Router. Los motores de búsqueda no reconocen esto como enlaces al igual que un `<a href="http://example.com">` en HTML, por lo que interpretarán cada página como si estuviera aislada. Para remediar esto, a partir de ahora, al añadir una redirección a otra página, se debería realizar con enlaces en vez de botones que llaman a acciones.

## 4. Menos carga dinámica en listados

Si hay un listado, como el de ofertas o el de empresas, y no se renderiza todo a la misma vez, cualquier contenido de ese listado que se renderice en la misma página mediante acción del usuario (como un botón de *Ver más*) será invisible para las arañas web. La versión actual de la aplicación no contiene casos de esto, pero si en un futuro hay que añadir mecanismos así debido al gran número de empresas y ofertas disponibles, se debe priorizar utilizar mecanismos de paginación más tradicionales antes que carga dinámica.

## 5. Añadir etiquetas

Por defecto, React usa una sola URL (para hacer una *single page application*, o SPA) y los metadatos se encuentran solo en las cabeceras de esta página. Normalmente, esto impide hacer un buen uso de los elementos `<meta>` que permiten definir una descripción para motores de búsqueda. Una solución a este problema es [React Helmet](https://www.npmjs.com/package/react-helmet), un paquete que permite añadir etiquetas a componentes específicos.

Las etiquetas más importantes para el SEO son los siguientes:

- `<title>`: no es un *meta tag*, pero establece el título de la página, tanto en la pestaña que se muestra en la parte superior del navegador como en los resultados de búsqueda. Debe ser breve (máximo entre 50 y 60 caracteres) y directo.
- `<meta name="description">`: una descripción o resumen de la página. Debe ser breve, aunque no tanto como el título (máximo entre 150 y 160 caracteres) y usar palabras clave.
- `<meta name="keywords">`: indica al motor de búsqueda las palabras clave con las que quiere que se busque una página. **Nota: algunos buscadores, como Google, ignoran esta etiqueta**, pero otros la siguen utilizando.

Las imágenes y los vídeos también pueden ser optimizados para motores de búsqueda. A estos se les puede añadir texto alternativo que no solo permite dar más información sobre la imagen a los buscadores, sino que también mejora la accesibilidad de la página, al darle a los lectores de pantalla una descripción de la imagen.

Para que se muestren más detalles de la página al compartir enlaces de la misma por redes sociales, se pueden utilizar las etiquetas de gráfico abierto. Estas son `<meta property=”og:X”>` donde X es `title`, `description`, `type`, `image`, `url` o `site_name`.
