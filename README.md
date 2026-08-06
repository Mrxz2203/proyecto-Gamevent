# GamEvent — Organización de Eventos Privados

Landing page estática construida con **Astro** y **Tailwind CSS** para GamEvent, una empresa que organiza bodas, cumpleaños, eventos corporativos y reuniones sociales. El sitio presenta la marca, sus servicios, portafolio de trabajos realizados, testimonios de clientes, preguntas frecuentes y un formulario de contacto que redirige a WhatsApp.

## 🚀 Stack técnico

- **[Astro](https://astro.build/)** — generador de sitios estáticos, componentes `.astro`
- **Tailwind CSS** (`@import "tailwindcss"`) — utilidades de estilo
- **astro:assets** (`<Image />`) — optimización automática de imágenes (compresión, formatos modernos, tamaños responsive)
- Tipografías: **Playfair Display** (títulos) e **Inter** (texto), vía Google Fonts
- JavaScript nativo (sin frameworks de UI) para interactividad: menú móvil, header con scroll, acordeón de FAQ (`<details>`/`<summary>`)

## 📁 Estructura del proyecto

```
src/
├── layouts/
│   └── Layout.astro          # Layout base: <html>, meta SEO/Open Graph/Twitter Card, fuentes, estilos globales
├── pages/
│   └── index.astro           # Página principal: ensambla todas las secciones
├── styles/
│   └── global.css            # Import de Tailwind CSS
├── assets/
│   └── images/                # Imágenes optimizadas por astro:assets (hero, about, services, portfolio, testimonials)
└── components/
    ├── layout/
    │   ├── Header.astro       # Header sticky, transparente sobre el Hero, sólido al hacer scroll; menú móvil
    │   ├── Navbar.astro       # Enlaces de navegación (reutilizado en escritorio y móvil)
    │   └── Footer.astro       # Logo, redes sociales, enlaces rápidos, servicios, contacto, copyright
    ├── sections/
    │   ├── Hero.astro         # Portada con imagen de fondo y llamados a la acción
    │   ├── AboutUs.astro      # Sección "Nosotros": propuesta de valor + estadísticas
    │   ├── Services.astro     # Grid de servicios (Bodas, Cumpleaños, Corporativo, Social)
    │   ├── Portfolio.astro    # Galería de trabajos realizados con detalle expandible
    │   ├── Testimonials.astro # Testimonios de clientes con calificación en estrellas
    │   ├── FAQ.astro          # Preguntas frecuentes en acordeón accesible (HTML nativo)
    │   └── ContactForm.astro  # Info de contacto + formulario que arma un mensaje de WhatsApp
    └── ui/
        ├── Logo.astro         # Logo SVG inline, con variantes de color (gold / light / dark)
        ├── Button.astro       # (vacío — pendiente)
        └── Card.astro         # (vacío — pendiente)
```

## ✨ Características

- **Header dinámico**: transparente sobre el Hero, cambia a fondo sólido con blur y sombra al superar el umbral de scroll; incluye menú hamburguesa animado en móvil.
- **Logo SVG reutilizable** con tres variantes de color (`gold`, `light`, `dark`) para adaptarse a distintos fondos.
- **Sección de servicios** con tarjetas que revelan la descripción al hacer hover.
- **Portafolio interactivo**: cada proyecto se expande (`<details>`) para mostrar una descripción sin necesidad de JavaScript adicional.
- **Testimonios con grid adaptable**: el layout cambia automáticamente según la cantidad de testimonios (1, 2, o 3+).
- **FAQ accesible** usando `<details>`/`<summary>` nativo, sin JavaScript extra.
- **Formulario de contacto**: como Astro genera un sitio estático, el formulario no envía datos a un backend; en su lugar arma un mensaje precargado y redirige a WhatsApp. El código incluye una nota para conectar un servicio real (Web3Forms o Formspree) más adelante.
- **SEO y redes sociales**: metaetiquetas Open Graph y Twitter Card configuradas en `Layout.astro`.
- Totalmente **responsive**, con imágenes optimizadas (`widths`, `sizes`, formato `webp`) mediante `astro:assets`.

## 🛠️ Instalación y uso

```bash
# Instalar dependencias
npm install

# Modo desarrollo
npm run dev

# Build de producción
npm run build

# Vista previa del build
npm run preview
```

## ⚙️ Configuración pendiente

- **WhatsApp**: reemplazar el número de placeholder (`51999999999`) en `ContactForm.astro` por el número real de GamEvent.
- **Redes sociales**: actualizar los enlaces de Instagram, Facebook y TikTok en `Footer.astro` (actualmente apuntan a las URLs base de cada red).
- **Componentes UI**: `Button.astro`, `Card.astro` y `SectionTitle.astro` están creados pero vacíos, pendientes de implementación.
- **Imágenes**: el proyecto espera assets en `src/assets/images/` organizados por sección (`hero/`, `about/`, `services/`, `portfolio/`, `testimonials/`), además de `public/favicon.svg` y `public/og-image.webp`.

## 📬 Contacto (datos mostrados en el sitio)

- **Teléfono / WhatsApp:** +51 999 999 999 *(placeholder)*
- **Correo:** contacto@gamevent.com
- **Ubicación:** Lima, Perú