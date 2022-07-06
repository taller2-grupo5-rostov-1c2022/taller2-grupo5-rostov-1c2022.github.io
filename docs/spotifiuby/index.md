---
layout: home
title: Spotifiuby
nav_order: 1
permalink: docs/
has_children: true
---

# Spotifiuby

<!-- button class="btn js-toggle-dark-mode">Modo oscuro</!-->

Spotifiuby es un servicio de reproducción de música.
Busca ofrecer distintos tipos de contenido, tanto en forma de canciones como en forma de
álbumes y playlists. Cuenta, además, con servicios adicionales, como el de mensajería privada.

El proyecto consta fundamentalmente de tres componentes:

- [**Aplicación Móvil**](/docs/app/) \
  con la cual el usuario interactúa para buscar música y reproducirla.
- [**Backoffice Web**](/docs/backoffice/) \
  para que los administradores gestionen el servicio.
- [**Backend**](/docs/backend/) \
  que se encarga de proveer todos los servicios necesarios para el funcionamiento de las aplicaciones.

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = 'Modo oscuro';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = 'Modo claro';
  }
});
</script>
