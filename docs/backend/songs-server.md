---
layout: default
title: Contenido y usuarios
parent: Backend
nav_order: 1
---


### [Servicio de contenido y usuarios](https://github.com/taller2-grupo5-rostov-1c2022/songs-server)

* Es un **monolito de contenido y usuarios**, lo cual simplifica las relaciones entre el contenido y los usuarios.
* **Contenido**: canciones, playlists, álbumes, comentarios, reviews, favoritos
* **Verificación y autorización**: permite el bloqueo y modificación de contenido, así como también el acceso
a contenido bloqueado por parte de los administradores.
* **Base de datos relacional**: la información se encuentra fuertemente relacionada.
Por ejemplo, un usuario puede tener varias playlists; una playlist puede tener varias canciones; una canción puede
encontrarse en varias playlists.