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
  <strong>Revisión</strong>
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

# Contribuciones del Equipo

| Nombre(s) y Apellido(s) | Tipo de Contribución |
| --- | --- |
| Adriana Vento Conesa | Redacción Comportamiento de Suscripciones |
| [Placeholder] | [Placeholder] |
| [Placeholder] | [Placeholder] |


# Tabla de Contenidos

1. [Resumen Ejecutivo](#1-resumen-ejecutivo)
2. [Datos para la Revisión](#2-datos-para-la-revisión)
3. [Ofertas](#3-ofertas)
    - [Comportamiento de las Suscripciones](#311-comportamiento-de-las-suscripciones)
4. [Autentificación](#4-autentificación)
    - [Log-in](#41-login)
    - [Registro](#42-registro)
5. [Transportistas](#5-transportista)
6. [Empresas](#6-empresas)
7. [Reseñas](#7-reseñas)
8. [Suscripciones](#8-suscripciones)


## 1. Resumen Ejecutivo

Este documento proporciona una guía detallada para revisar la aplicación web de *matchmaking* de camioneros. Incluye un mapeo explícito de los casos de uso (UC) a las interacciones en el software, datos necesarios para la revisión, requisitos del sistema y un enlace a la demostración.

## 2. Datos para la Revisión

En esta tabla aparece toda la información necesaria para la revisión de Camyo.

| Información | Detalles |
| --- | --- |
| Url de la Organización de Github | https://github.com/Camyo-ISPP |
| Url del repositorio de Github | https://github.com/Camyo-ISPP/CamyoApp |
| Url del repositorio de Documentación | https://github.com/Camyo-ISPP/Documentacion |
| Url de la Landing Page | https://sites.google.com/view/camyo-landing-page/ |
| Url del despliegue Frontend | https://ispp-2425-g5-s2-fafe6.web.app/ |
| Url de la herramienta de seguimiento  | https://app.clockify.me/login |
| Credenciales para la herramienta de seguimiento  | Email: [profesores.camyo@gmail.com](mailto:profesores.camyo@gmail.com)<br>Contraseña de la cuenta de google: Profesores.camyo!01 <br> Para acceder, hagan login con este email y recibirán un correo al correo con el código para acceder. |
| Requisitos potenciales para usar el sistema | Ninguno. |
| Url de la demo | [Reemplazar!] |
| Usuario de Empresa (Camyo) | **Usuario:** emp_etsii1  **Contraseña:** etsiipass<br>**Usuario:** emp_etsii2  **Contraseña:** etsiipass |
| Usuario de Camionero(Camyo) | **Usuario:** cam_etsii1  **Contraseña:** etsiipass<br>**Usuario:** cam_etsii2  **Contraseña:** etsiipass (Autónomo) |
| Usuario Administrador  | **Usuario:** admin  **Contraseña:** etsiipass |

## 3. Ofertas

### 3.1 Crear Oferta

Al acceder a la plataforma como empresa, podrás crear ofertas para camioneros desde tu perfil. Para hacerlo, debes rellenar los campos requeridos según el tipo de oferta que quieras publicar, ya sea de carga o de trabajo. Tras publicarla, esta oferta será visible para el resto de usuarios.

![image]()

![image]()

![image]()

Sin embargo, el número de ofertas activas que puedes tener simultáneamente depende del nivel de tu suscripción actual:

- **Suscripción Gratis**: Puedes tener hasta **1 oferta activa**.
- **Suscripción Básica**: Puedes tener hasta **3 ofertas activas**.
- **Suscripción Premium**: No hay límite en el número de ofertas activas.

#### 3.1.1 Comportamiento de las Suscripciones

En la pantalla de creación de ofertas, verás un botón para crear una nueva oferta. Este botón cambiará su estado según las siguientes condiciones:

- Si aún no has alcanzado el límite de ofertas permitidas por tu suscripción:
  - El botón estará habilitado y podrás crear una nueva oferta.

![image](https://i.imgur.com/EwcgGR6.png)

- Si has alcanzado el límite de ofertas activas permitidas:
  - El botón se bloqueará y mostrará el mensaje **"Límite de Ofertas Alcanzado"**.

![image](https://i.imgur.com/2mRysoa.png)

## 4. Autentificación

## 5. Transportista

### 5.1 Chat
Una vez iniciado sesión como transportista se podrá acceder a la pantalla de mensajería mediante la barra de navegación, en el apartado de "Mis Mensajes".

<p align="center">
<img src="images/barrachat.png">
</p>

En la pantalla de chats se podrán ver los chats abiertos. Una vez que se seleccione el chat, se abrirá automáticamente a la derecha de la lista, por lo que se podrá comenzar a enviar y recibir mensajes.

<p align="center">
<img src="images/chatcam.png">
</p>


## 6. Empresas

### 6.1 Chat
Una vez iniciado sesión como empresa se podrá acceder a la pantalla de mensajería mediante la barra de navegación, en el apartado de "Mis Mensajes".

<p align="center">
<img src="images/barrachat2.png">
</p>

En la pantalla de chats se podrán ver los chats abiertos. Una vez que se seleccione el chat, se abrirá automáticamente a la derecha de la lista, por lo que se podrá comenzar a enviar y recibir mensajes.

<p align="center">
<img src="images/chatemp.png">
</p>

## 7. Reseñas
### 7.1 Reseñas empresas
Una vez registrado como empresa, en su perfil, podemos ver si dicha empresa tiene o no alguna reseña y su valoración media.

<p align="center">
<img src="images/resena_miperfilempresa.png">
</p>

También pueden ver las reseñas de la empresa cualquier otro usuario.

<p align="center">
<img src="images/resena_publicempresa.png">
</p>

### 7.2 Reseñas camioneros
Una vez registrado como camionero, en su perfil, podemos ver si dicho camionero tiene o no alguna reseña y su valoración media.

<p align="center">
<img src="images/resena_miperfilcamionero.png">
</p>

También pueden ver las reseñas del camionero cualquier otro usuario.

<p align="center">
<img src="images/resena_publiccamionero.png">
</p>

### 7.3 Crear y editar reseñas
Un usuario podrá crear una reseña pulsando en el botón "Escribir reseña".

<p align="center">
<img src="images/resena_crear.png">
</p>

<p align="center">
<img src="images/resena_creada.png">
</p>

Luego, el usuario pulsando el botón "Editar reseña" podra editar la reseña. 

<p align="center">
<img src="images/resena_editar.png">
</p>


## 8. Suscripciones

Al acceder a la plataforma como empresa, se podrá acceder a la pantalla de planes de suscripción, donde se podrá cambiar de suscripción pulsando en el botón indicado según el tipo de plan al que se desee cambiar.

<p align="center">
<img src="images/suscripcion.png">
</p>







