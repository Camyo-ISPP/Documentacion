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
2. [Crawlers y prerrenderizado](#2-crawlers-y-prerrenderizado)  
  2.1. [Controlar crawlers](#21-controlar-crawlers)
3. [Enlazado interno](#3-enlazado-interno)
4. [Menos carga dinámica en los listados](#4-menos-carga-dinámica-en-listados)
5. [Añadir etiquetas](#5-añadir-etiquetas)
6. [Google Search Console](#6-google-search-console)  
  6.1. [Sitemap](#61-sitemap)
7. [Datos estructurados](#7-datos-estructurados)
8. [Palabras clave](#8-palabras-clave)  
  8.1. [Herramientas para la búsqueda y el análisis de palabras clave](#81-herramientas-para-la-búsqueda-y-el-análisis-de-palabras-clave)  
  8.2. [Listado de palabras clave](#82-listado-de-palabras-clave)  
  8.3. [Propuesta de crear un blog o publicaciones para optimizar para estas palabras clave](#83-propuesta-de-crear-un-blog-o-publicaciones-para-optimizar-para-estas-palabras-clave)

## 1. Introducción

La optimización de motores de búsqueda (*search engine optimisation* en inglés, de donde provienen las siglas **SEO**) consiste en una serie de técnicas y procesos que buscan aumentar el tráfico que recibe un sitio web por los motores de búsqueda, herramientas que devuelven enlaces relevantes según las búsquedas de los usuarios. Para Camyo, utilizar SEO es una buena manera de hacer que la aplicación pueda ser encontrada con más facilidad, al aumentar el puesto en el que aparece en los resultados de las búsquedas de usuarios potenciales.

Este documento tiene el fin de evaluar las distintas técnicas de SEO que podrían ser utilizadas en Camyo, cómo utilizarlas y las palabras clave que definen mejor a nuestra aplicación y que deberían devolver Camyo como resultado al buscarlas.

## 2. Crawlers y prerrenderizado

Los motores de búsqueda más populares hacen uso de arañas web (*web crawler*) para encontrar sitios web. Las páginas encontradas mediante *crawling* son indizadas, para recopilar etiquetas y atributos como el idioma, la fecha de creación/actualización y la localización geográfica de la página.

Sin embargo, estas etiquetas y atributos no son suficientes para describir la finalidad de la página. Ya que Camyo usa React Native, los contenidos se renderizan en el cliente. Por tanto, los motores de búsqueda no pueden acceder a la mayoría de la información que se encuentra en estas páginas web, debido a que suelen leer solo o mayoritariamente el HTML.

Para solucionar este problema, existen soluciones de mercado que permiten prerrenderizar páginas y así optimizarlas para las arañas web. [Prerender.io](https://prerender.io/) es la herramienta más popular para el SEO de páginas web con JavaScript.

### 2.1. Controlar crawlers

Sin embargo, no todas las páginas deberían ser accedidas por las arañas web (por ejemplo, paneles de admin o la interfaz de pago). Para estos casos, se debe añadir un archivo `robots.txt` en la raíz del sitio web que establezca un listado de direcciones dentro del sitio web que los bots no tendrán permitido acceder. Más información acerca de este tipo de archivo está disponible en [robotstxt.org](https://www.robotstxt.org/robotstxt.html).

Hay una directiva en el archivo `robots.txt` que establece con qué frecuencia las arañas pueden *crawlear* el sitio web. En el caso de Googlebot, hay que establecer esta frecuencia en Google Search Console (véase [6. Google Search Console](#6-google-search-console)). Con esta herramienta, además de poder controlar la actividad de los *crawlers*, se pueden recibir informes de la misma y descubrir errores o posibles problemas con el sitio web que afectan al comportamiento de los *crawlers*.

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

## 6. [Google Search Console](https://search.google.com/search-console/about?hl=es-419)

Google dispone de una herramienta para *webmasters* llamada Google Search Console que permite, entre otras funcionalidades:

- Comprobar errores de indizado, spam u otros problemas detectados por Googlebot
- Recibir estadísticas de acceso a la página por Googlebot
- Mostrar qué paginas, tanto internas como externas, están enlazadas con el sitio web
- Escribir un archivo robots.txt y probarlo
- Enviar un *sitemap*
- Ver reportes de velocidad

Todas estas funciones pueden ser de ayuda para la optimización de Camyo.

### 6.1. Sitemap

Un sitemap es un archivo XML con un listado de los enlaces de un sitio web. En el caso de Camyo, si no se cambian los botones para convertirlos en `<a href>`, la araña web no podrá ver qué páginas de Camyo están enlazadas entre ellas. Por tanto, crear un *sitemap* permitiría proveerle a los motores de búsqueda un archivo en lenguaje de ordenador estructurado de forma que se vean los contenidos enlazados. [SEO Spider](https://www.screamingfrog.co.uk/seo-spider/) es un buen ejemplo de una herramienta que permite generar un *sitemap* automáticamente para sitios web con un número reducido de enlaces.

Tras crear y enviar el *sitemap*, es importante analizar si este contiene mucho contenido duplicado, o si contiene demasiadas páginas que aportan poco valor al usuario. Esto también se puede comprobar desde Google Search Console.

## 7. Datos estructurados

Google utiliza varios tipos de datos estructurados según la especificación de Schema.org. Estos se muestran de otra forma en las búsquedas. En vez de mostrar solo un resultado con el enlace, el título, una descripción y una imágen del sitio web, pueden mostrar mucha más información relevante al usuario sin que este tenga que hacer clic para antes descubrirla. En el caso de Camyo, puede ser muy útil [JobPosting](https://developers.google.com/search/docs/appearance/structured-data/job-posting), ya que muestra un resumen de ofertas de empleo. Para utilizar datos estructurados, hay que añadir código JSON-LD en la cabeza o el cuerpo de la página web. En el caso de páginas web que usan JavaScript, como Camyo, [hay un procedimiento específico para generar estos datos.](https://developers.google.com/search/docs/appearance/structured-data/generate-structured-data-with-javascript)

## 8. Palabras clave

### 8.1. Herramientas para la búsqueda y el análisis de palabras clave

Para encontrar las mejores palabras clave, es necesario conocer el mercado al que va dirigida la página web, las modas actuales y cómo lo hacen nuestros competidores.

#### [Google Trends](https://trends.google.com/trends/)

A pesar de no ser una herramienta específicamente diseñada para la búsqueda de palabras clave, permite ver qué es lo más popular en el momento y la evolución de la popularidad de distintos términos de búsqueda. Además, ofrece puntuaciones divididas por comunidad autónoma, permitiendo así realizar optimización o campañas publicitarias localizadas. Es una herramienta gratuita.

#### Google Search Console

La anteriormente mencionada Google Search Console permite ver qué consultas llevan a nuestro sitio web y analizar las impresiones, los clics y la posición del mismo en las búsquedas de Google.

#### [Semrush Keyword Magic Tool](https://es.semrush.com/analytics/keywordmagic/start)

Crea palabras clave a partir de una palabra clave inicial, ofreciendo estadísticas como tráfico, volumen y la dificultad de optimizar una página para esas palabras clave. Necesita registro para utilizarse.

#### [WordStream Free Keyword Tool](https://www.wordstream.com/keywords)

Herramienta gratuita y sin registro para la sugerencia de palabras clave a partir de una palabra clave inicial o una página web. Además de palabras clave, devuelve el volumen de búsquedas, la competencia y la rentabilidad mínima y máxima.

#### [Keywordtool.io](https://keywordtool.io)

Ofrece un buscador sencillo para encontrar palabras clave similares a la búsqueda. Sin embargo, la información más útil (volumen de búsquedas, competencia, moda y CPC) no está disponible sin una suscripción.

#### [Ahrefs Website Traffic Checker](https://ahrefs.com/traffic-checker)

Permite ver estimaciones del tráfico de otros sitios web. Ofrece información limitada en su plan gratuito (estimación y valor del tráfico, top 5 de países, top 5 palabras clave, top 5 subdominios).

#### [SimilarWeb](https://www.similarweb.com/)

Parecida a la anterior, con más detalles para el análisis de competidores. Ofrece la misma información que la anterior sin registrarse, además de un listado de competidores.

### 8.2. Listado de palabras clave

Tras utilizar WordStream y Ahrefs Website Traffic Checker para analizar palabras clave de nuestros competidores más similares y más populares y filtrar las propias de su marca o página web o las más genéricas con las que es más difícil competir, estas son algunas palabras clave para las que podemos optimizar:

- servicio de transporte de carga
- servicios transporte de carga
- servicio de transporte de mercancias
- servicios transportistas
- transporte de cargo
- soluciones de gestion de transporte
- bolsa de cargas
- bolsa de carga
- empresa de transporte cercana
- empresas de transporte cercanas
- empresa de logistica cercana
- empresas de logistica cercanas
- transporte de vehiculos
- transporte de coches
- transporte de motos
- empleo conductor
- empleo camionero
- empleo transportista
- empleo de camionero
- empleo de transportista
- ofertas de empleo transportista
- ofertas de empleo de transportista
- ofertas de empleo camionero
- ofertas de empleo de camionero
- ofertas de trabajo transportista
- ofertas de trabajo de transportista
- ofertas de trabajo camionero
- ofertas de trabajo de camionero
- trabajos de transportista
- trabajo de transportista
- trabajos de camionero
- trabajo de camionero
- bolsa de trabajo camionero
- bolsa de trabajo transportista
- empresas de transporte que necesitan conductores
- empresas de transporte que necesitan camioneros
- empresas de logistica que necesitan conductores
- empresas de logistica que necesitan camioneros
- empresas de logistica que necesitan transportistas
- carta de porte
- carnet de camion
- carnet camion
- renovar cap

Y con ayuda de de Semrush Keyword Magic Tool, podemos encontrar algunas palabras más que están relacionadas a las de la lista. De aquí, encontramos:

- ofertas de empleo transporte y logistica
- bolsa de carga para camioneta
- bolsa de carga transporte ligero
- bolsa de carga para camiones
- bolsa de carga express
- camionero empleo
- empresas que necesitan servicio de transporte de carga
- empresas que solicitan servicio de transporte de carga
- servicios de transporte de carga terrestre
- carnet c de camion
- autoescuela para carnet de camion
- que tipo de camion puedo conducir con el carnet c
- empresa de transporte por camion
- empresa de transporte de mercancias
- empresas de transporte de carga
- trabajo de camionero en españa
- empleo de camionero en españa
- como trabajar de camionero en españa
- como trabajar de transportista en españa

### 8.3. Propuesta de crear un blog o publicaciones para optimizar para estas palabras clave

Como parte de la presencia en redes sociales que buscamos tener durante este sprint, podríamos realizar publicaciones centradas en algunas de las palabras clave de la lista, para así aparecer más fácilmente en los resultados de búsqueda. Esta sugerencia viene de mi observación propia. Muchas de las empresas que ofrecen un servicio online que aparecen en los primeros resultados de búsquedas lo hacen escribiendo un artículo o publicación en un blog propio que busca responder a una pregunta u ofrecer información sobre algunos términos de búsqueda y, dentro de la publicación, relacionarlo con el servicio que ofrecen, para así tratar de obtener nuevos usuarios. Crear un blog no solo nos daría un SEO mejor, sino que además permitiría enlazar las publicaciones de este con las que hacemos en redes sociales. 
