---
layout: default
title: Desarrollo
parent: Spotifiuby
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

# Organización del Proyecto

> Algunos de los siguientes requieren que se de acceso.

- [Organización en Github](https://github.com/taller2-grupo5-rostov-1c2022) \
  donde se encuentran todos los repositorios de la plataforma

- [Organización de Firebase](https://console.firebase.google.com/u/0/project/rostov-spotifiuby/overview) \
  posee servicios útiles para el proyecto, tales como registro, autenticación, base de datos.

- [Data Dog](https://app.datadoghq.com/infrastructure) \
  servicio de monitoreo de los servidores de la plataforma.

- [Tablero de Trello](https://trello.com/b/Kjg4LeEq/spotifiuby) \
  para administrar las épicas, historias de usuario y tareas semanales

- [Bitácora del Proyecto](https://docs.google.com/spreadsheets/d/1tFkrxioVGcj9Yy4X5Gez2n8S7ZMc2SEv-AUj2vXuvrg/edit#gid=0) \
  para realizar un seguimiento del progreso del proyecto con el transcurso de las entregas

- [Drive del Proyecto](https://drive.google.com/drive/folders/1VBf7WqJRDxUy6D87TiZ9oYl1o_7uy96w?usp=sharing) \
  para almacenar archivos relacionados del proyecto

# Análisis Post-Mortem

## Cambios en la Base de Datos

Inicialmente tuvimos un par de inconvenientes donde al realizar cambios en la base de datos durante el desarrollo, ya sea de manera accidental o a conciencia, los servicios de back-end dejaban de funcionar correctamente en producción y por ende también en el front-end.

Para solucionar esto optamos por desplegar un ambiente de desarrollo en paralelo, con sus propios servidores y bases de datos para los servicios de canciones/usuarios y mensajería. \
Ademas, empleamos [Alembic](https://alembic.sqlalchemy.org/en/latest/) para gestionar los cambios en las bases de datos.

## Consumo de Cuota de Almacenamiento

Se dieron un par de instancias donde perdimos acceso a los servicios de almacenamiento de firebase debido a exceder la cuota de uso.

Pudimos solucionar esto efectivamente realizando ciertas optimizaciones en el back-end, como utilizar urls publicas en vez de privadas (que requerían acceder al recurso por cada petición) y alternativas que nos permitían obtener la dirección del recurso sin generar una petición del mismo; de modo que minimizamos los accesos al almacenamiento.

Ademas, se aprovecho para implementar una funcionalidad donde el servidor agrega a la uri del recurso un timestamp de ultima modificación como query parameter; de modo que el front-end no debe revalidar el recurso si no ha cambiado y adaptándose "sin costura" a la cache de recursos.
