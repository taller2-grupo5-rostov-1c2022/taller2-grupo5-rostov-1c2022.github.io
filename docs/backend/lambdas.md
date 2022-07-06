---
layout: default
title: Lambdas
parent: Backend
nav_order: 7
---

<details open markdown="block">
  <summary>
	Contenidos
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Funciones Lambda

## Servicios

Algunas funcionalidades han sido desplegadas como funciones Lamba, ya sea debido a que son muy sencillas o debido a prestaciones necesarias.

### Evento de Métricas &nbsp; [`/metricsEvent`](https://github.com/taller2-grupo5-rostov-1c2022/Lambda/tree/master/metricsEvent)

Se llama esta función cuando queremos almacenar una métrica en la base de datos.
Como por ejemplo un recupero de contraseña.

Se uso una función debido a la simplicidad de la transacción.

### Refresco de Suscripciones &nbsp; [`/refreshSubscriptions`](https://github.com/taller2-grupo5-rostov-1c2022/Lambda/tree/master/refreshSubscriptions)

Esta función se ejecuta una vez por dia de manera automática, y se encarga de refrescar las suscripciones de los usuarios.
Esto lo hace mediante un endpoint habilitado en el servidor de usuarios y contenido.

Se utilizo una función debido a la habilidad de ejecutarla de manera programada.

## Acceso

Estas funciones se despliegan manualmente a AWS

- Código Fuente : [GitHub](https://github.com/taller2-grupo5-rostov-1c2022/Lambda)
