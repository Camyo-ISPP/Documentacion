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
  <strong>Plan de pruebas</strong>
</h1>

<p align="center">
  <strong>Nombre del Entregable:</strong> Sprint 3 
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
| Pedro Jiménez Guerrero | Redacción del documento |

## Tabla de Contenidos

1. [Alcance](#alcance)
2. [Estrategia de pruebas](#estrategia-de-pruebas)
    - [Pruebas unitarias](#pruebas-unitarias)
    - [Pruebas de integración](#pruebas-de-integración)
    - [Pruebas de aceptación](#pruebas-de-aceptación)
    - [Pruebas de rendimiento](#pruebas-de-rendimiento)
4. [Resultados](#resultados)
    - [Pruebas unitarias](#pruebas-unitarias-1)
    - [Pruebas de integración](#pruebas-de-integración-1)
    - [Pruebas de aceptación](#pruebas-de-aceptación-1)
    - [Pruebas de rendimiento](#pruebas-de-rendimiento-1)
5. [Conclusión](#conclusion)

## Alcance

- Se realizarán únicamente las pruebas mostradas en las píldoras teóricas de clase.
- Sólo se someterán a las pruebas el código generado por los componentes del grupo.
- Inicialmente se realizarán las pruebas que involucren sólo el backend de la aplicación (tests unitarios y de integración), las de rendimiento y las de aceptación. 
- Si el alcance del proyecto lo permite se realizarán las pruebas que incluyen al frontend (tests end-to-end y exploratorio).
- No se realizarán pruebas sobre aspectos que no se traten en la asignatura, como seguridad avanzada o hacking.
 
## Estrategia de pruebas 

### Pruebas unitarias

El objetivo de estas pruebas es conseguir que los tests tengan una **cobertura mínima del 90% del código**.

Para hallar todos los posibles fallos en el código se seguirá el **happy path** de cada método para comprobar la funcionalidad principal, así como **casos de prueba negativos** para comprobar que todos los errores esperados están cubiertos y que los datos introducidos sean válidos.

Para ahorrar tiempo de desarrollo las pruebas unitarias de los servicios y repositorios se harán de forma simultánea, probando así también la integración de los dos componentes.

#### Herramientas

Para estas pruebas se usará [JUnit](https://junit.org/junit5/) y el soporte del framework Spring Boot.
 
#### Escenarios de prueba:

- Tests de controlador y servicio de la autenticación.
- Tests de controlador, servicio y repositorio de la entidad `Camionero`.
- Tests de controlador, servicio y repositorio de la entidad `Empresa`.
- Tests de controlador, servicio y repositorio de la entidad `Oferta`.
- Tests de controlador, servicio y repositorio de la entidad `Carga`.
- Tests de controlador, servicio y repositorio de la entidad `Trabajo`.
- Tests de controlador de la entidad `Pago`.
- Tests de controlador, servicio y repositorio de la entidad `Reseña`.
- Tests de controlador, servicio y repositorio de la entidad `Suscripción`.
- Tests de servicio y repositorio de la entidad `Authorities`.
- Tests de controlador, servicio y repositorio de la entidad `Usuario`.

### Pruebas de integración

El objetivo de estas pruebas es comprobar que tanto los **componentes internos** de la aplicación como los **externos** **interactúen correctamente** entre ellos.

Para comprobar esto nos centraremos en la integración de la **base de datos** con la capa de servicio y la **API de Stripe** con el controlador de la entidad `Pago`

#### Herramientas

Para estas pruebas se usará [JUnit](https://junit.org/junit5/) y el soporte del framework Spring Boot.


#### Escenarios de prueba

- **Integración con la base de datos**:
  1. Arrancar aplicación.
  1. Guardar datos relevantes para el test del servicio que se vaya a realizar.
  1. Verificar que los datos obtenidos son los esperados en cada prueba.

- **Integración con servicios externos**:
  1. Arrancar aplicación.
  1. Usar métodos del controlador de la entidad `Pago` que usen el servicio externo de Stripe.
  1. Verificar que los datos recibidos del servicio son los esperados.

### Pruebas de aceptación

El objetivo de estas pruebas es verificar que la aplicación **cumple con todos los requisitos** establecidos por el cliente, así cómo **asegurar la facilidad de uso** y la apariencia visual.

##### Herramientas

Para estas pruebas se usará el despliegue local de la aplicación para explorar manualmente los criterios anteriormente enumerados.

#### Criterios de aceptación

- **Para empresas**:
  - Ver ofertas propias y poder gestionar las solicitudes.
  - Ver perfil propio y poder editarlo.
  - Ver perfil de los transportistas y poner reseñas a aquellos que hayan trabajado con la empresa.
  - Publicar una oferta y que aparezca para el resto de usuarios.
  - Cambiar el tipo de suscripción y que se reflejen los cambios en la usabilidad.
  - Patrocinar una oferta y que aparezca la primera en el listado de ofertas. 
  - Chatear con los transportistas mediante mensajes instantáneos.
  - Una vez iniciada sesión, poder crear una oferta en menos de 3 clicks.
  - Una vez iniciada sesión, poder aceptar o rechazar a un transportista en menos de 3 clicks.
  

- **Para transportistas del transporte**:
  - Ver listado de ofertas y poder filtrarlas según los intereses del usuario.
  - Ver detalles de una oferta y poder solicitar el trabajo.
  - Ver perfil propio y poder editarlo.
  - Ver perfil de las empresas y poner reseñas a aquellas que hayan contratado al usuario.
  - Ver ofertas que ha solicitado el usuario y que se categoricen según el estado en el que se encuentran.
  - Chatear con las empresas que le interesan al usuario mediante mensajes instantáneos.
  - Acceder al listado de ofertas en un click.
  - Una vez iniciada sesión, poder solicitar una oferta en menos de 3 clicks.

### Pruebas de rendimiento

El objetivo de estas pruebas es verificar que la velocidad de la aplicación es aceptable para el usuario y no provoca rechazo. **El tiempo de respuesta de todas las llamadas deberá ser inferior a 2 segundos**.

Ya que por la naturaleza académica del proyecto no podemos contar con un entorno de pre-producción para realizar las pruebas en un entorno similar al de producción, se harán en el despliegue local.

#### Herramientas

Para estas pruebas se usará [JMeter](https://www.baeldung.com/jmeter) 

#### Escenarios de prueba:
- Se medirá la velocidad a la que cargan los siguientes aspectos de la aplicación:
  - Página principal
  - Listado de ofertas y empresas
  - Registro e inicio de sesión 
  - Publicación de ofertas y patrocinio

## Resultados

### Pruebas unitarias



### Pruebas de Integración



### Pruebas de aceptación



### Pruebas de rendimiento



## Conclusión




