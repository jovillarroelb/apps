# SMERA | Portal de Aplicaciones

Repositorio base para la gestión centralizada del subdominio `apps.smera.cl`. 

Este proyecto actúa como el **Directorio Raíz (Portal de Acceso)** de las aplicaciones web desarrolladas bajo la marca SMERA Strategic Intelligence. Su objetivo es proporcionar una interfaz limpia, corporativa y escalable para el acceso a las distintas herramientas y módulos de la organización.

## Arquitectura de Despliegue

La infraestructura utiliza **GitHub Pages** con una estrategia de repositorios independientes para maximizar la modularidad y reducir el riesgo de caídas cruzadas entre aplicaciones.

- **URL Principal:** `https://apps.smera.cl` (Gestionada por este repositorio `apps`).
- **Aplicaciones Secundarias:** Cada aplicación se aloja en su propio repositorio (ej. `bingo`) y es servida nativamente como un subdirectorio (ej. `https://apps.smera.cl/bingo`) gracias a la herencia del dominio raíz en GitHub Pages.

## Configuración de DNS

Este repositorio está vinculado al dominio personalizado mediante GoDaddy. La configuración requiere un registro CNAME:
- **Tipo:** CNAME
- **Host:** apps
- **Apunta a:** `[TU-USUARIO].github.io`

*Nota: La seguridad SSL (HTTPS) es impuesta nativamente a través de la configuración de GitHub Pages de este repositorio raíz.*

## Guía para integrar una nueva aplicación

Para añadir un nuevo módulo al ecosistema `apps.smera.cl`, se deben seguir tres pasos:

1. **Crear el Repositorio de la App:** Crear un nuevo repositorio público (o privado según el plan de GitHub) con el nombre exacto de la ruta deseada (ej. `nueva-app`).
2. **Activar GitHub Pages:** En el nuevo repositorio, activar GitHub Pages desde la rama principal. **Importante:** No configurar ningún _Custom Domain_ en este repositorio secundario.
3. **Actualizar el Directorio Raíz:** Modificar el archivo `index.html` de este repositorio (`apps`) agregando una nueva tarjeta (card) dentro de la sección `.app-grid` que apunte al directorio relativo (`/nueva-app`).

## Soporte y Mantenimiento

Para modificaciones de diseño o estructura, el archivo `index.html` contiene el CSS integrado (`<style>`) que define las variables de identidad visual de SMERA (colores, tipografía corporativa y diseño de tarjetas modulares).
