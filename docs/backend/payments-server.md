---
layout: default
title: Pagos
parent: Backend
nav_order: 2
---

<details open markdown="block">
  <summary>
	Contenidos
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Servicio de pagos

* Orientado a interactuar con el **Smart Contract.**
* Crea la **wallet** para cada usuario de la aplicación.
* Persiste la información de cada **transacción** realizada en el sistema, tanto desde un usuario hacia la plataforma como desde la plataforma hacia un usuario.

En [este link](https://github.com/taller2-grupo5-rostov-1c2022/payments-server) se puede acceder al repositorio.

# Documentación OpenAPI

La documentación referida a la especificación OpenAPI del servicio se puede encontrar en [https://github.com/taller2-grupo5-rostov-1c2022/payments-server#api-documentation](https://github.com/taller2-grupo5-rostov-1c2022/payments-server#api-documentation)
Por problemas con [Fastify-Swagger](https://github.com/fastify/fastify-swagger), no se pudo generar un Swagger como sí lo tienen los demás servicios.

# Estado de badges

[![Production pipeline](https://github.com/taller2-grupo5-rostov-1c2022/payments-server/actions/workflows/pipeline.yml/badge.svg?branch=master)](https://github.com/taller2-grupo5-rostov-1c2022/payments-server/actions/workflows/pipeline.yml)
[![codecov](https://codecov.io/gh/taller2-grupo5-rostov-1c2022/payments-server/branch/master/graph/badge.svg?token=htOzOZRHPV)](https://codecov.io/gh/taller2-grupo5-rostov-1c2022/payments-server)
[![](https://img.shields.io/badge/Node-12.18.1-green.svg)](https://nodejs.org/en/)
![Fastify](https://img.shields.io/badge/fastify-%23000000.svg?style=for-the-badge&logo=fastify&logoColor=white)

**Aclaración:** `Pipeline` incluye linter-tests (coverage)-deploy

# Deploy

## Heroku

El deploy hacia Heroku se encuentra automatizado dentro del [pipeline de GitHub Actions](https://github.com/taller2-grupo5-rostov-1c2022/payments-server/blob/master/.github/workflows/pipeline.yml)
usando la imagen de Docker del servicio en desarrollo. En particular, se necesitan las siguientes
[variables de entorno](https://github.com/taller2-grupo5-rostov-1c2022/payments-server#heroku) para generar el deploy automático.

## Local

### Usando Docker

Se cuenta con soporte para utilizar `Docker` de manera de no instalar todas las dependencias necesarias para el proyecto directamente.
Las instrucciones se encuentran [acá](https://github.com/taller2-grupo5-rostov-1c2022/payments-server/tree/master#docker).

### Usando npm

En caso de optar por levantar el proyecto de manera local, se puede usar `npm` para instalar las dependencias. Tener en
cuenta que se necesita `PostgreSQL` instalado previamente para la base de datos. Las instrucciones se encuentran [acá](https://github.com/taller2-grupo5-rostov-1c2022/payments-server/tree/master#dependencies)

# Tests

La ejecución de los tests se encuentra automatizada a la hora de deployar mediante el [pipeline de GitHub Actions](https://github.com/taller2-grupo5-rostov-1c2022/payments-server/blob/master/.github/workflows/pipeline.yml).
Al mismo tiempo, si se requiere correr los tests de manera local, se puede ejecutar con `npm run test` (recordar
que se necesita `PostgreSQL` instalado previamente), o directamente utilizar `Docker` con sus [instrucciones](https://github.com/taller2-grupo5-rostov-1c2022/payments-server/tree/master#running-tests-within-container).

# Configuración variables de entorno

Las variables de entornos utilizadas, ya sea configuradas de manera local, mediante los `secrets` de GitHub, o config var en Heroku;
son las siguientes:

- `DATABASE_URL:` URI de la DB a usar, requerida tanto como variable de entorno local y en Heroku. El archivo `docker-compose.yml` provee la URL automáticamente.
- `DD_API_KEY:` API key de DataDog, requerida como config var en Heroku.
- `DD_DYNO_HOST:` sirve agrupar hosts en DataDog, requerida como config var en Heroku.
- `DD_TAGS:` tags para DataDog, requerida como config var en Heroku.
- `API_KEY:` API key del servicio para realizar requests al mismo, requerida tanto como variable de entorno local y en Heroku.
- `HEROKU_APP_NAME:` nombre de la app en Heroku, requerida como action secret.
- `HEROKU_EMAIL:` mail de la cuenta de Heroku utilizada para el deploy, requerida como action secret.
- `CODECOV_TOKEN:` token de codecov, requerido como action secret para subir reportes de coverage mediante el pipeline de GitHub Actions.
- `INFURA_API_KEY:` la API key para el nodo de Infura, se puede obtener una desde el [Infura dashboard](https://infura.io/dashboard). Se requiere tanto como variable de entorno local y config var en Heroku.
- `MNEMONIC:` El mnemonic para la wallet, se puede obtener una desde MetaMask. Se requiere tanto como variable de entorno local y config var en Heroku.
- `PORT:` El puerto en el que debe correr el server. Por defecto es el 3000 y se requiere como variable de entorno local.
- `ETHERSCAN_API_KEY:` La API key para Etherscan, se puede obtener una desde el [Etherscan dashboard](https://etherscan.io/myapikey). Se requiere tanto como variable de entorno local y config var en Heroku.