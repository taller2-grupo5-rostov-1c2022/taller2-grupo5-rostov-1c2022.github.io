---
layout: default
title: Contenido y usuarios
parent: Backend
nav_order: 1
---

<details open markdown="block">
  <summary>
	Contenidos
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>


# [Servicio de contenido y usuarios](https://github.com/taller2-grupo5-rostov-1c2022/songs-server)

- Es un **monolito de contenido y usuarios**, lo cual simplifica las relaciones entre el contenido y los usuarios.
- **Contenido**: canciones, playlists, álbumes, comentarios, reviews, favoritos.
- **Verificación y autorización**: permite el bloqueo y modificación de contenido, así como también el acceso
a contenido bloqueado por parte de los administradores.
- **Base de datos relacional**: la información se encuentra fuertemente relacionada.
Por ejemplo, un usuario puede tener varias playlists; una playlist puede tener varias canciones; una canción puede
encontrarse en varias playlists.

En [este link](https://github.com/taller2-grupo5-rostov-1c2022/songs-server) se puede acceder al repositorio.

# Documentación OpenAPI

La documentación referida a la especificación OpenAPI del servicio se puede encontrar en https://rostov-song-server.herokuapp.com/docs, la
cual fue generada automáticamente por `FastAPI`.

# Estado de badges

[![Pipeline](https://github.com/taller2-grupo5-rostov-1c2022/songs-server/actions/workflows/pipeline.yml/badge.svg?branch=master)](https://github.com/taller2-grupo5-rostov-1c2022/songs-server/actions/workflows/pipeline.yml)
[![codecov](https://codecov.io/gh/taller2-grupo5-rostov-1c2022/songs-server/branch/master/graph/badge.svg?token=LJIu1T1HQr)](https://codecov.io/gh/taller2-grupo5-rostov-1c2022/songs-server)
[![](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/)
[![](https://img.shields.io/badge/docs-fastapi-blue.svg)](https://fastapi.tiangolo.com/)

# Deploy

## Heroku

## Local

### Usando Docker

### Usando poetry

# Configuración variables de entorno