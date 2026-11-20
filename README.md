# Práctica Docker: web minimalista

Práctica del bootcamp de Full Stack de The Bridge.

## Qué es

Una web de portfolio metida en un contenedor de Docker. La web es la misma que maqueté en [web-personal](https://github.com/jbalaguersalas/web-personal): el portfolio de Sarah Chen, una estudiante de diseño que no existe. El bootcamp nos dio el diseño en Figma y yo lo pasé a HTML y CSS.

En esta práctica lo nuevo es Docker. La web la sirve un nginx desde un contenedor, así que no hace falta abrir el archivo a mano.

## Qué hice

- Tres páginas: `index.html` (la portada con cinco proyectos), `about.html` y `project.html` (el detalle de un proyecto).
- Un solo `styles.css` con nombres de clase BEM, por ejemplo `project-card__title` o `nav__link--active`.
- Diseño pensado primero para móvil. Luego añadí media queries a 600px, 800px y 1280px para que en pantallas grandes cada tarjeta ponga el texto a un lado y la imagen al otro.
- Un `Dockerfile` de dos líneas: parte de `nginx:alpine` y copia la web a la carpeta que sirve nginx.
- Un `compose.yaml` con un servicio `web` que construye esa imagen y une el puerto 8080 de mi ordenador con el 80 del contenedor.
- Un `.dockerignore` para que no entren en la imagen ni `.git`, ni el README, ni los propios archivos de Docker.

## Cómo verlo

Con Docker Desktop abierto, desde la carpeta del proyecto:

```bash
docker compose up --build
```

Después abre <http://localhost:8080> en el navegador.

Para pararlo:

```bash
docker compose down
```

También funciona sin Compose:

```bash
docker build -t web-minimalista .
docker run -p 8080:80 web-minimalista
```

## README original

El repositorio empezó con este README que crea GitHub:

```
# -Pr-ctica-Docker-Web-Minimalista---
```
