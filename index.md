---
layout: home
title: Introducción
nav_order: 1
---


Spotifiuby es un servicio de reproducción de música.
Busca ofrecer distintos tipos de contenido, tanto en forma de canciones como en forma de
álbumes y playlists. Cuenta, además, con servicios adicionales, como el de mensajería privada.
El proyecto consta fundamentalmente de tres componentes
- Una aplicación móvil, con la cual el usuario interactúa para buscar música y reproducirla
- Un backend, que se encarga de buscar y almacenar la información de los usuarios y el contenido
- Un backoffice web, desde el cual un administrador puede realizar distintas tareas de gestión y monitoreo

<button class="btn js-toggle-dark-mode">Modo oscuro</button>

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