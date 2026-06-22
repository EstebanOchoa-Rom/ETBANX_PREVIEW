# Arquitectura del proyecto

Este documento describe la organización de carpetas y archivos del proyecto **Etbanx**, construido con Astro y Tailwind CSS.

## 📁 Estructura de carpetas

```
etbanx/
├── public/
│   ├── images/
│   └── screenshots/
│
├── src/
│   ├── content/
│   │   ├── knowledge/
│   │   ├── labs/
│   │   ├── research/
│   │   ├── projects/
│   │   ├── notes/
│   │   └── config.ts
│   │
│   ├── components/
│   │   ├── ui/
│   │   ├── layout/
│   │   ├── map/
│   │   ├── content/
│   │   └── effects/
│   │
│   ├── layouts/
│   ├── pages/
│   ├── styles/
│   ├── utils/
│   └── config/
│
├── docs/
│   └── references/
│
├── astro.config.mjs
├── tailwind.config.mjs
├── tsconfig.json
└── package.json
```

## 📌 Descripción de carpetas clave

### `public/`
Archivos estáticos servidos directamente sin procesamiento: imágenes, screenshots y otros recursos.

### `src/content/`
Colecciones de contenido tipadas mediante Astro Content Collections (`config.ts` define los esquemas):

- **knowledge/** — Artículos de conocimiento general.
- **labs/** — Experimentos y pruebas técnicas.
- **research/** — Documentos de investigación.
- **projects/** — Fichas de proyectos.
- **notes/** — Notas rápidas.

### `src/components/`
Componentes reutilizables divididos por responsabilidad:

- **ui/** — Componentes de interfaz genéricos (botones, cards, inputs, etc.).
- **layout/** — Componentes estructurales (header, footer, sidebar).
- **map/** — Componentes relacionados a mapas o visualización de relaciones entre contenido.
- **content/** — Componentes para renderizar contenido (artículos, listas, tags).
- **effects/** — Animaciones y efectos visuales.

### `src/layouts/`
Plantillas base que envuelven las páginas (layout general, layout de artículo, etc.).

### `src/pages/`
Rutas del sitio. Cada archivo `.astro` aquí se convierte en una página.

### `src/styles/`
Hojas de estilo globales y configuración adicional de Tailwind.

### `src/utils/`
Funciones auxiliares reutilizables (formateo de fechas, helpers de contenido, etc.).

### `src/config/`
Configuración general del sitio (metadatos, navegación, constantes).

### `docs/`
Documentación del proyecto. `references/` contiene material de referencia visual (capturas, diagramas, imágenes de apoyo).

## 🔄 Flujo de datos

1. El contenido se escribe en Markdown/MDX dentro de `src/content/`.
2. Astro valida ese contenido contra los esquemas definidos en `config.ts`.
3. Las páginas en `src/pages/` consultan las colecciones y renderizan el contenido usando los componentes de `src/components/`.
4. Los layouts en `src/layouts/` envuelven el resultado final con la estructura visual común del sitio.