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

**Aclaración:** `Pipeline` incluye linter-tests (coverage)-deploy

# Deploy

## Heroku

El deploy hacia Heroku se encuentra automatizado dentro del [pipeline de GitHub Actions](https://github.com/taller2-grupo5-rostov-1c2022/songs-server/blob/master/.github/workflows/pipeline.yml)
usando la imagen de Docker del servicio en desarrollo. En particular, se necesitan las siguientes
[variables de entorno](https://github.com/taller2-grupo5-rostov-1c2022/songs-server#heroku).

## Local

### Usando Docker

Se cuenta con soporte para utilizar `Docker` de manera de no instalar todas las dependencias necesarias para el proyecto directamente.
Las instrucciones se encuentran [acá](https://github.com/taller2-grupo5-rostov-1c2022/songs-server#docker).

### Usando poetry

En caso de optar por levantar el proyecto de manera local, se puede usar `poetry` para instalar las dependencias. Tener en
cuenta que se necesita `PostgreSQL` instalado previamente para la base de datos. Las instrucciones se encuentran [acá](https://github.com/taller2-grupo5-rostov-1c2022/songs-server#installing-the-project)

# Tests

La ejecución de los tests se encuentra automatizada a la hora de deployar mediante el [pipeline de GitHub Actions](https://github.com/taller2-grupo5-rostov-1c2022/songs-server/blob/master/.github/workflows/pipeline.yml).
Al mismo tiempo, si se requiere correr los tests de manera local, se puede ejecutar con `poetry run pytest` (recordar
que se necesita `PostgreSQL` instalado previamente), o directamente utilizar `Docker` con sus [instrucciones](https://github.com/taller2-grupo5-rostov-1c2022/songs-server#running-tests-within-container).

# Configuración variables de entorno

Las variables de entornos utilizadas, ya sea configuradas de manera local, mediante los `secrets` de GitHub, o config var en Heroku;
son las siguientes:

- `POSTGRES_URL:` URI de la DB a usar, requerida tanto como variable de entorno local y en Heroku.
- `DD_API_KEY:` API key de DataDog, requerida como config var en Heroku.
- `DD_DYNO_HOST:` sirve agrupar hosts en DataDog, requerida como config var en Heroku.
- `DD_TAGS:` tags para DataDog, requerida como config var en Heroku.
- `API_KEY:` API key del servicio para realizar requests al mismo, requerida tanto como variable de entorno local y en Heroku.
- `TESTING:` denota una especie de entorno de desarrollo, para poder testear fácilmente usando mocks de los servicios externos que lo requieran.
- `HEROKU_API_KEY:` API key de la cuenta utilizada para deployar en Heroku, requerida como action secret.
- `HEROKU_APP_NAME:` nombre de la app en Heroku, requerida como action secret.
- `HEROKU_EMAIL:` mail de la cuenta de Heroku utilizada para el deploy, requerida como action secret.
- `CODECOV_TOKEN:` token de codecov, requerido para subir reportes de coverage mediante el pipeline de GitHub Actions.
- `AGORA_APP_CERT:`
- `AGORA_APP_ID:`
- `FIREBASE_ID:`
- `FIREBASE_KEY:`