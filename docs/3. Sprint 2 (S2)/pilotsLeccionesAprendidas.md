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
  <strong>Lecciones aprendidas en pilotaje</strong>
</h1>

<p align="center">
  <strong>Nombre del Entregable:</strong> Sprint 2  
</p>
<p align="center">
  <strong>Asignatura:</strong> Ingeniería del Software y Práctica Profesional  
</p>
<p align="center">
  <strong>Curso:</strong> 2024-2025  
</p>

### Contribuciones del Equipo

| Nombre(s) y Apellido(s)       | Tipo de Contribución          |
|-------------------------------|-------------------------------|
| Pedro Jiménez Guerrero        | Conversión de word a MD, estructura feedback Sprint 1 y caso de uso "ver listado oferta" (Sprint 1)         |
| [Nombre Apellido]             | [Tipo de Contribución]        |
| [Nombre Apellido]             | [Tipo de Contribución]        |

## Tabla de Contenidos

1. [Introduccón](#introducción)
2. [Sprint 0](#sprint-0)
2. [Sprint 1](#sprint-1)
    - [Caso de uso: Ver listado de oferta](#caso-de-uso-ver-listado-de-ofertas)
    - [Caso de uso: Solicitar una oferta](#caso-de-uso-solicitar-una-oferta)
    - [Caso de uso: Registro de camionero](#caso-de-uso-registro-de-camionero)
    - [Caso de uso: Publicar una oferta de empleo](#caso-de-uso-publicar-una-oferta-de-empleo)
    - [Caso de uso: Gestión (editar/eliminar) de ofertas publicadas ](#caso-de-uso-gestión-editareliminar-de-ofertas-publicadas)
    - [Caso de uso: Registro de empresa](#caso-de-uso-registro-de-empresa)
1. [Sprint 2](#sprint-2)
1. [Sprint 3](#sprint-3)

## Introducción 

Este documento recoge el análisis y conclusiones sobre el feedback recibido por los usuarios pilotos durante los diferentes periodos de pruebas. 

Habrá un total de tres periodos de pruebas, correspondientes a cada sprint de desarrollo, de los cuales obtendremos información muy preciada de parte de los usuarios pilotos. 

Además, consideraremos como Sprint 0 el feedback obtenido durante el proceso de selección de usuarios pilotos, mediante las encuestas y contactos con profesionales del sector de logística y transporte. 

 

## Sprint 0 

A fecha de la redacción de este documento, se han recibido 16 respuestas en la encuesta de transportistas y 7 en la dirigida a empresas.  

### Transportistas 

#### Datos generales 

El perfil de usuarios que tenemos es diverso, con casi un 70% que lleva más de 10 años en el sector y el mismo porcentaje son trabajadores por contrato. Sólo el 30% de los encuestados son conductores autónomos. 

La mayoría de los encuestados busca trabajo en el sector mediante contactos personales y el contacto directo con empresas, siendo los que usan las nuevas tecnologías una minoría. El problema principal que se encuentran es la gran cantidad de páginas que deben buscar, así como la dificultad de contactar a empresas de transporte y las malas condiciones laborales. Cabe destacar que un usuario autónomo habla directamente con una agencia de transportes. 

#### Funcionalidades 

Las funcionalidades más destacadas son: 

- Filtrar ofertas 

- Ver información completa de la oferta 

- Facilidad de uso 

- Historial de trabajos realizados 

- Registro de ofertas a las que se han inscrito 

Uno de los encuestados es autónomo y destaca la importancia de hablar directamente con la empresa para aclarar detalles tales como la localización de la carga, si está a pie de calle, planta baja, o hay que bajarla antes de transportarla. Esta información podría uno de los parámetros que se desbloquean como datos extra en la suscripción Basic de las empresas. 

Además, hace hincapié en lo importante de que las ofertas estén bien remuneradas y no sean una puja a quién pide menos, sino que se establezcan tarifas adecuadas. Quizá se podría implementar un sistema automático de cálculo de tarifas por distancia y tipo/peso de mercancía, con un parámetro opcional que sirva de incentivo para que la oferta sea elegida con mayor rapidez. 

 

### Personal de empresas 

#### Necesidades y modelo de negocio 

Las empresas contactadas listan como principal reto la escasez de conductores cualificados, así como la dificultad al encontrar conductores comprometidos tanto a largo plazo como autónomos. 

La mayoría contactan a sus trabajadores mediante el boca a boca, seguido de portales de empleo genéricos, además de que a un 57% le parece bien aunar los perfiles de autónomo y asalariado en un mismo lugar, por lo que la adopción de Camyo será bien recibida. Cabe destacar que un 43% remarcó que a veces no interesa ambos tipos de perfiles, por lo que es importante que en la aplicación quede recogida esas dos secciones. 

Los servicios por el que consideran pagar son herramientas para filtrar candidatos y un sistema de valoraciones a transportistas, además de un soporte prioritario. Cabe destacar que sólo un usuario estaría dispuesto a pagar las estadísticas de las ofertas publicadas. Estas características serán estudiadas para planificar su adición durante el desarrollo, se discutirá la implementación y en qué planes de suscripción añadirlos. 

En cuanto a los precios, las respuestas son bastante dispares, pero dos usuarios coinciden en que el plan Basic debería rondar los 10-20€, mientras que el Premium los 20-40€. Hay que destacar que un usuario sobresalió en los precios del plan Basic y Premium sugiriendo 50€ y 150€ respectivamente, además de otro encuestado que considera que el primer plan de los mencionados debería ser gratis y el último pagar por uso. 

Dos usuarios dieron sugerencias adicionales. Uno de ellos dijo que ya existen plataformas de este tipo, por lo que es posible que las características distintivas del producto no queden claras al usuario promedio. El otro dio una serie de datos que le gustaría ver en la aplicación: 

- Disponibilidad del conductor. 

- Gestiones de rutas nacionales o internacionales (no queda muy claro a qué se refiere). 

- Qué capacidades de conducción tiene el transportista (tipos de remolques a utilizar). 

 

#### Funcionalidades 

Los encuestados dan más importancia a la contratación a largo plazo en contraposición a la contratación de autónomos. Tampoco consideran muy importante tener la opción de mostrar toda la información de la oferta, aunque sí aprecian gestionar ofertas forma simultánea y filtrar candidatos para elegir el tipo de trabajador que necesitan. Hay que destacar que uno de los encuestados expresa que el problema es que no se encuentran conductores. 

Las empresas le dan importancia a la posibilidad de poder ver estadísticas de sus ofertas, así como contar con un sistema de comunicación directa con los candidatos, si bien hay algunos que prefieren usar herramientas de comunicación externas. Aunque haya algunos que no la consideren necesaria, la posibilidad de patrocinar ofertas también es vista con buenos ojos, aunque cabe destacar que hay quien prefiere que los patrocinios sólo afecten a las ofertas según la cercanía geográfica al usuario. 

Algunas de las funcionalidades que destacan a la hora de facilitar la gestión de ofertas es un sistema de alertas que avise cuándo un candidato se ha inscrito a una oferta, además de poder acceder a un historial con información sobre el desempeño de las ofertas. Por tanto, es importante ofrecer a las empresas un sistema claro y legible en el que puedan ver sus ofertas, sus estadísticas, y los trabajadores que se hayan presentado. 

De forma adicional, uno de los encuestados sugirió añadir un sistema de valoraciones también para empresas, de forma que aquellas que ofrezcan buenas condiciones prevalezcan sobre el resto. Esto casa bien con la preocupación de los conductores por encontrar buenas empresas, por lo que es importante tomar esto en cuenta y añadir un sistema de valoraciones para empresas que muestre la satisfacción de los trabajadores con ella. 

 



## Sprint 1 

A fecha de la redacción de este documento, se han recibido 23 respuestas de lo usuarios piloto, y una puntuación media de 6,91

### Caso de uso: Ver listado de ofertas

#### Feedback de prioridad crítica:

- Las ofertas tardan mucho en cargar
    - Sugerencias de los usuarios: 
        - Crear una landing page inicial y cargar las ofertas en segundo plano para que el usuario no se percate
        - Guardar las ofertas en localStorage/sessionStorage o usando React Query (que sería la mejor práctica)
        - Añadir paginación
- La licencia mostrada en la preview no coincide con la que se muestra en los detalles de la oferta
    - Sugerencias de los usuarios:
        - Se ha dado en un caso en el que la licencia era "C+E" y mostraba "C". Sugiere que esto se debe a que internamente la licencia se trata como "C_E" y esa "_" corte la vista de la licencia a mostrar.

#### Feedback de prioridad media:

- Hay un nicho bastante importante de trabajo en las furgonetas, tanto reparto diario como transporte de paquetería urgente.
    - Añadir los tipos de furgoneta al vehículo requerido en oferta
- No se señalan las ofertas que ya se han solicitado
    - Añadir algún marcador o icono que lo indique
- Uno de los usuarios piloto no sabía qué es Camyo
    - Añadir landing page para presentar e invitar a probar el producto
- No quedaba claro qué indicaba el apartado de las licencias ya que sólo aparecía la letra
    - Añadir el nombre de cada parámetro. P.ej: "Licencia mínima requerida: C"
- Indicar al lado del sueldo si es por mes, por día, por carga...
- Las imágenes e iconos no aparecen
- Sugerencias: 
    - Vista de mosaico para ver más ofertas sin tener que scrollear tanto
    - Añadir a la preview de oferta la jornada y la fecha de incorporación
    - Añadir en la preview un desplegable con los detalles de la oferta (para las cargas)
    - Añadir en la preview un botón para solicitar la oferta directamente, evitando así tiempos de carga innecesarios.

#### Feedback de prioridad baja:

- Que sea más atractivo visualmente
    - Añadir un fondo al listado o a la página
    - No se debe tener muy en cuenta ya que al resto de usuarios les ha parecido correcto el diseño
-  Referirnos a "territorio nacional" en vez de "nivel nacional"
- Que el dinero y el botón de solicitar no estén en el extremo derecho de la línea puede generar incomodidad visual.
- En los chips donde se muestra información de la oferta (p.ej: "trabajo/carga", licencia "C") no está bien  centrado el texto.

#### Feedback positivo:

- Funcionamiento correcto, claro e intuitivo.
- Buena paleta de colores
- Tamaño de letra adecuado, si acaso aumentar un poco la fuente del nombre de la oferta, p. ej. "Conductor de carga pesada"

### Caso de uso: Solicitar una oferta



### Caso de uso: Registro de camionero



### Caso de uso: Publicar una oferta de empleo

 

### Caso de uso: Gestión (editar/eliminar) de ofertas publicadas



### Caso de uso: Registro de empresa 

 

 

## Sprint 2 

 

 

 

 

 

## Sprint 3 

 

 