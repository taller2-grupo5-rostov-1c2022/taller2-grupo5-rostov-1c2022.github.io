---
layout: home
title: Spotifiuby
nav_order: 1
---

# Introducción




# Arquitectura y tecnologías utilizadas

La aplicación fue desarrollada en una arquitectura de microservicios.

![Arquitectura](./images/Taller2%20-%20Diagramas%20-%20Arquitectura.png)

## Descripción de los microservicios

### [Servicio de contenido y usuarios](https://github.com/taller2-grupo5-rostov-1c2022/songs-server)

* Es un **monolito de contenido y usuarios**, lo cual simplifica las relaciones entre el contenido y los usuarios.
* **Contenido**: canciones, playlists, álbumes, comentarios, reviews, favoritos
* **Verificación y autorización**: permite el bloqueo y modificación de contenido, así como también el acceso
a contenido bloqueado por parte de los administradores.
* **Base de datos relacional**: la información se encuentra fuertemente relacionada.
Por ejemplo, un usuario puede tener varias playlists; una playlist puede tener varias canciones; una canción puede
encontrarse en varias playlists.

### [Servicio de pagos](https://github.com/taller2-grupo5-rostov-1c2022/payments-server)

* Orientado a interactuar con el Smart Contract
* Crea la wallet para cada usuario de la aplicación
* Persiste la información de cada transacción realizada en el sistema

### [Servicio de mensajes](https://github.com/taller2-grupo5-rostov-1c2022/messages-server)

* Se encarga de la **mensajería** entre usuarios.
* **Base de datos no relacional**: ya que no existen muchas relaciones entre las entidades.
Una conversación entre dos usuarios consiste simplemente en una lista de mensajes.

### [Servicio de notificaciones](https://github.com/taller2-grupo5-rostov-1c2022/notifs-server)

* Envía **notificaciones push** a los dispositivos. Para lograrlo, debe adminitrar
los **tokens** de los usuarios.
* Cuando un usuario inicia sesión, se genera un token de sesión que es almacenado en la base de datos.


# Organizacion del proyecto

* [Organizacion en Github](https://github.com/taller2-grupo5-rostov-1c2022):
donde se encuentran todos los repositorios de la plataforma

* [Organización de Firebase](https://console.firebase.google.com/u/0/project/rostov-spotifiuby/overview):
posee servicios útiles para el proyecto, tales como registro, autenticación, base de datos.

* [Tablero de Trello](https://trello.com/b/Kjg4LeEq/spotifiuby):
para administrar las épicas, historias de usuario y tareas semanales