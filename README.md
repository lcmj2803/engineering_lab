# Engineering Lab | Plantilla inicial para GitHub Pages

Esta es una web estática **sin Node.js, sin React, sin instalaciones y sin JavaScript obligatorio**. Incluye una escena base inspirada en el mockup, tres enlaces invisibles colocados sobre los equipos, tres páginas de proyecto y tarjetas accesibles para móviles.

## 1. Probar en Visual Studio Code

1. Extrae el archivo ZIP y abre la carpeta `engineering-lab-starter` en VS Code.
2. Abre `index.html` en tu navegador. También puedes ejecutar `python3 -m http.server 8000` dentro de esta carpeta y visitar `http://localhost:8000/`.
3. Pulsa el robot, el banco RF y la consola PID. Deben abrir sus páginas.

## 2. Publicar en GitHub Pages

1. Crea un repositorio público, por ejemplo `engineering-lab`.
2. Sube **el contenido de la carpeta**, no una carpeta adicional que contenga todo. `index.html` debe quedar en la raíz del repositorio.
3. En GitHub ve a **Settings → Pages → Build and deployment → Source: Deploy from a branch**.
4. Selecciona **Branch: main**, **Folder: /(root)**, después **Save**.
5. La dirección será normalmente `https://TU-USUARIO.github.io/engineering-lab/`. Sustituye `TU-USUARIO` por tu nombre real de usuario de GitHub. Si tu repositorio se llama `TU-USUARIO.github.io`, será la web principal `https://TU-USUARIO.github.io/`.

Guía de GitHub: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 3. Editar los proyectos

- `index.html`: título, descripción de entrada, enlaces interactivos, tarjetas y sección “Sobre mí”.
- `projects/swarm-bb.html`: texto, arquitectura, pruebas del robot.
- `projects/banda-x.html`: texto y evidencias del sensor.
- `projects/pid-analogico.html`: texto y resultados de simulación del PID.
- `styles.css`: colores, diseño y animaciones CSS.
- `assets/laboratorio.webp`: **ilustración de fondo**. Está aplanada, es decir, los objetos NO son modelos 3D editables por separado.

Para agregar una fotografía: copia el archivo a `assets/fotos/` y pon una etiqueta en la página de proyecto, por ejemplo:

```html
<img src="../assets/fotos/robot-real.jpg" alt="Prototipo físico de swarm_bb" width="600">
```

Para añadir el enlace al repositorio, reemplaza el bloque de galería por un enlace real:

```html
<a href="https://github.com/TU-USUARIO/TU-REPO" target="_blank" rel="noopener noreferrer">Ver código en GitHub ↗</a>
```

## 4. Añadir un cuarto proyecto

A. Copia `projects/pid-analogico.html` como `projects/nuevo-proyecto.html` y modifica título, encabezado, contenido y estado.

B. En `index.html`, dentro de `<div class="project-grid">`, duplica una tarjeta y cambia su título, descripción y enlace:

```html
<a class="project-card" href="projects/nuevo-proyecto.html">
  <div class="card-icon" aria-hidden="true">🧪</div>
  <span class="number">04 / NUEVA ESTACIÓN</span>
  <h3>Nuevo proyecto</h3>
  <p>Una frase que explique el proyecto.</p>
  <span class="card-action">Entrar al proyecto ↗</span>
</a>
```

C. **Si también quieres un objeto físico dentro de la habitación**, primero tendrás que actualizar `assets/laboratorio.webp` con una nueva ilustración que lo incluya. Después agrega un nuevo `<a class="hotspot">` dentro de `<div class="scene">` en `index.html`, ajustando `--x`, `--y`, `--w` y `--h` como porcentajes de la imagen:

```html
<a class="hotspot" href="projects/nuevo-proyecto.html"
   aria-label="Abrir nuevo proyecto"
   style="--x: 40%; --y: 48%; --w: 16%; --h: 20%;">
  <span class="hotspot-label">🧪 Explorar nuevo proyecto ↗</span>
</a>
```

D. No es necesario programar en JavaScript para estos cambios. Más adelante podrías usar modelos GLB/GLTF, Three.js o `<model-viewer>` para mostrar equipos 3D genuinos, sin sustituir todo el sitio.

## 5. Lista antes de publicar la versión final

- [ ] Cambiar los textos genéricos por información verificable de cada proyecto.
- [ ] Añadir tus fotos y videos reales.
- [ ] Confirmar el estado actual de pruebas y validación.
- [ ] Añadir enlaces públicos de repositorios y CV.
- [ ] Probar con ratón, teclado y móvil.
- [ ] Revisar imágenes y textos en inglés cuando quieras habilitar más idiomas.

**Nota:** La imagen principal es un mockup aplanado con áreas de clic. No es una sala tridimensional navegable ni permite mover cada objeto independientemente. Es la forma más simple de lanzar una V1 ligera, bonita y útil.
