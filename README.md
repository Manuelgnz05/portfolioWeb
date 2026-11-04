<div align="center">

# 🌿 Portfolio · Manuel González Caballero

**Mi portfolio personal como desarrollador web: una single-page hecha con Astro, con contenido dirigido por datos, tema claro/oscuro y un cursor personalizado.**

![Astro](https://img.shields.io/badge/Astro-7-BC52EE?logo=astro&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-strict-3178C6?logo=typescript&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![Node](https://img.shields.io/badge/Node-%E2%89%A5%2022.23.4-5FA04E?logo=node.js&logoColor=white)

</div>

<!--
  💡 Cuando tengas la web publicada, añade aquí una captura:
  1. Guarda la imagen en docs/preview.png
  2. Descomenta la línea siguiente

  ![Vista previa del portfolio](docs/preview.png)
-->

---

## 📑 Índice

- [Sobre el proyecto](#-sobre-el-proyecto)
- [Características](#-características)
- [Tecnologías](#-tecnologías)
- [Estructura del proyecto](#-estructura-del-proyecto)
- [Primeros pasos](#-primeros-pasos)
- [Comandos disponibles](#-comandos-disponibles)
- [Editar el contenido](#-editar-el-contenido)
- [Personalizar el diseño](#-personalizar-el-diseño)
- [Despliegue](#-despliegue)
- [Hoja de ruta](#-hoja-de-ruta)
- [Autor](#-autor)

---

## ✨ Sobre el proyecto

Este repositorio contiene el código de mi portfolio web. Está pensado para presentar de un vistazo quién soy, qué sé hacer y en qué he trabajado, todo en una única página con navegación por secciones.

La idea central es **separar el contenido del diseño**: textos, proyectos, estudios o idiomas viven en archivos JSON, y los componentes de Astro se encargan de pintarlos. Así puedo actualizar la web sin tocar el marcado.

## 🚀 Características

- **Single-page con secciones:** Inicio, Skills, Educación, Idiomas, Experiencia, Proyectos, Certificaciones y Contacto.
- **Navegación con scroll suave** y desplazamiento ajustado por sección, con la sección activa resaltada en el menú mediante `IntersectionObserver`.
- **Tema claro y oscuro** con un botón flotante. La preferencia se guarda en `localStorage` y se recuerda en la siguiente visita.
- **Contenido dirigido por datos:** seis archivos JSON alimentan las secciones de la página.
- **Educación en formato "historial de git":** cada etapa se muestra como una rama con *commit*, ficheros cambiados e inserciones/eliminaciones.
- **Barras de habilidades** con color y porcentaje propios para cada tecnología.
- **Descarga directa del currículum** en PDF.
- **Cero JavaScript de framework en cliente:** Astro genera HTML estático y solo se envía el JS de los pequeños scripts de interacción.

## 🛠️ Tecnologías

| Tecnología | Uso |
| :-- | :-- |
| [Astro](https://astro.build) | Framework, componentes `.astro` y generación estática |
| TypeScript (modo `strict`) | Scripts de interacción dentro de los componentes |
| HTML5 + CSS3 | Maquetación y estilos (CSS con ámbito por componente y variables globales) |
| JSON | Fuente de datos del contenido |
| [Roboto Serif](https://fonts.google.com/specimen/Roboto+Serif) | Tipografía, cargada desde Google Fonts |

## 📂 Estructura del proyecto

```text
portfolioWeb/
├── public/                     # Recursos estáticos (imágenes, iconos, CV en PDF, favicon)
├── src/
│   ├── components/
│   │   ├── ThemeToggle.astro   # Botón de tema claro/oscuro
│   │   ├── Menu.astro          # Barra de navegación y redes sociales
│   │   ├── Descripcion.astro   # Presentación y botones de contacto / CV
│   │   ├── Skills.astro        # Sección de habilidades  (usa Skill.astro)
│   │   ├── Educacion.astro     # Sección de educación    (usa Estudio.astro)
│   │   ├── Idiomas.astro       # Sección de idiomas      (usa Idioma.astro)
│   │   ├── Experiencia.astro   # Sección de experiencia  (usa Trabajo.astro)
│   │   ├── Proyectos.astro     # Sección de proyectos    (usa Proyecto.astro)
│   │   ├── Certificaciones.astro  # Certificaciones      (usa Certificacion.astro)
│   │   ├── Contacto.astro      # Formulario y tarjetas de contacto
│   │   └── Footer.astro        # Pie de página
│   ├── data/                   # 📦 Contenido editable en JSON
│   │   ├── skills.json
│   │   ├── educacion.json
│   │   ├── idiomas.json
│   │   ├── experiencia.json
│   │   ├── proyectos.json
│   │   └── certificaciones.json
│   ├── layouts/
│   │   └── Layout.astro        # Estructura HTML base, fuentes y variables de color
│   └── pages/
│       └── index.astro         # Página única que compone todas las secciones
├── astro.config.mjs
├── tsconfig.json
└── package.json
```

## 🏁 Primeros pasos

### Requisitos

- [Node.js](https://nodejs.org) **22.23.4 o superior** (definido en `engines` de `package.json`)
- npm (incluido con Node)

### Instalación

```bash
# 1. Clona el repositorio
git clone https://github.com/Manuelgnz05/portfolioWeb.git

# 2. Entra en la carpeta
cd portfolioWeb

# 3. Instala las dependencias
npm install

# 4. Arranca el servidor de desarrollo
npm run dev
```

Abre <http://localhost:4321> en el navegador. Los cambios se recargan automáticamente.

## 🧞 Comandos disponibles

Todos los comandos se ejecutan desde la raíz del proyecto:

| Comando | Acción |
| :-- | :-- |
| `npm install` | Instala las dependencias |
| `npm run dev` | Inicia el servidor de desarrollo en `localhost:4321` |
| `npm run build` | Genera el sitio de producción en `./dist/` |
| `npm run preview` | Previsualiza localmente la build antes de desplegar |
| `npm run astro -- <comando>` | Ejecuta la CLI de Astro (`astro add`, `astro check`…) |

## 📝 Editar el contenido

Todo el contenido de la web se modifica en `src/data/`. No hace falta tocar los componentes: basta con editar, añadir o borrar elementos de cada JSON.

| Archivo | Sección | Campos de cada elemento |
| :-- | :-- | :-- |
| `skills.json` | Skills | `name`, `icon`, `color`, `percentage` |
| `educacion.json` | Educación | `id`, `branch`, `location`, `title`, `center`, `description`, `tags`, `filesIcon`, `filesChanged`, `insertions`, `deletions`, `date`, `calendarIcon`, `side` (`left` / `right`) |
| `idiomas.json` | Idiomas | `language`, `code`, `flagIcon`, `level`, `ribbonColors` |
| `experiencia.json` | Experiencia | `role`, `company`, `companyUrl`, `startDate`, `endDate`, `location`, `isCurrent` |
| `proyectos.json` | Proyectos | `id`, `title`, `image`, `description`, `githubUrl`, `liveUrl`, `technologies` (lista de `{ name, icon }`) |
| `certificaciones.json` | Certificaciones | `id`, `title`, `issuer`, `year`, `description`, `credentialUrl` |

**Ejemplo: añadir un proyecto**

```json
{
  "id": "mi-proyecto",
  "title": "Mi proyecto",
  "image": "proyecto4.png",
  "description": "Una breve descripción de qué hace y para quién.",
  "githubUrl": "https://github.com/Manuelgnz05/mi-proyecto",
  "liveUrl": "https://mi-proyecto.example.com",
  "technologies": [
    { "name": "Astro", "icon": "Astro_edited.png" },
    { "name": "JavaScript", "icon": "js.png" }
  ]
}
```

> 🖼️ **Imágenes e iconos:** los nombres de archivo de los JSON hacen referencia a ficheros de la carpeta `public/`. Añade ahí la imagen antes de usarla.
>
> 📄 **Currículum:** sustituye el PDF de `public/` manteniendo el mismo nombre de archivo, o actualiza el enlace en `Descripcion.astro`.

## 🎨 Personalizar el diseño

Los colores se controlan con variables CSS globales definidas en `src/layouts/Layout.astro`. El tema oscuro redefine esas mismas variables bajo la clase `dark-theme` del `<body>`.

```css
:root {
  --bg-main: #E0E0E0;
  --nav-bg: #E0E0E0;
  --nav-border: #6A6A6A;
  --text-title: #434343;
  --text-body: #A4A4A4;
  --card-bg: #2D2D2D;
  --card-header-bg: #434343;
  --card-footer-bg: #252525;
  --card-text: #E0E0E0;
  --accent-color: #AAB888;   /* color de acento de toda la web */
}
```

Cambiando `--accent-color` se actualizan a la vez los bordes del botón de tema y el resto de detalles de acento.

## 🌍 Despliegue

El proyecto genera un sitio **100 % estático**, así que se puede alojar en cualquier servicio de hosting estático (Netlify, Vercel, Cloudflare Pages, GitHub Pages…).

```bash
npm run build
```

## 🗺️ Hoja de ruta

Posibles mejoras para seguir puliendo la web:

- [ ] Diseño **responsive** para tablet y móvil
- [ ] Conectar el **formulario de contacto** a un servicio de envío (ahora mismo es solo la parte visual)
- [ ] Metadatos SEO y Open Graph para que se vea bien al compartir el enlace
- [ ] Mejoras de accesibilidad (navegación por teclado y foco visible, ya que los elementos de navegación son botones)
- [ ] Versión en inglés
- [ ] Añadir una licencia al repositorio

## 👤 Autor

**Manuel González Caballero**

- GitHub: [@Manuelgnz05](https://github.com/Manuelgnz05)
- LinkedIn: [Manuel González Caballero](https://www.linkedin.com/in/manuel-gonz%C3%A1lez-caballero/)

---

<div align="center">

Hecho con 💚 y [Astro](https://astro.build)

</div>