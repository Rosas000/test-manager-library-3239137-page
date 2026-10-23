# Manager Library — Page (sitio estático)

Sitio público estático de presentación del proyecto Manager Library. Muestra qué es el sistema, sus actores, historias principales y cómo acceder a la aplicación. No requiere backend ni base de datos para verse.

*Prueba técnica SDD · Ficha ADSO 3239137 · SENA · Viernes 23 de octubre de 2026*

## Stack

* HTML5
* CSS3 (Tailwind CDN)
* JavaScript mínimo
* Sin build
* Sin dependencias

## Arranque local

No requiere instalación. Solo abrir el archivo en el navegador:

```bash
# Opción 1: abrir directamente
start index.html

# Opción 2: servidor estático (opcional)
npx serve .
# → http://localhost:3000
```

### Con Docker:

```bash
docker build -t library-page .
docker run -p 3000:80 library-page
# → http://localhost:3000
```

## Estructura

```text
/
├── index.html          # Página principal (landing)
├── css/
│   └── styles.css      # Estilos personalizados (complementa Tailwind)
├── js/
│   └── main.js         # Interacciones mínimas (menú móvil, scroll)
├── img/
│   └── hero.png        # Imagen de portada
├── Dockerfile          # Nginx estático
└── README.md
```

## Secciones del sitio

| Sección | Contenido |
| --- | --- |
| **Hero** | Nombre del proyecto, descripción corta, CTA hacia la app |
| **¿Qué es?** | Propósito del sistema: biblioteca pequeña con catálogo, socios y préstamos |
| **Actores** | Administrador, bibliotecario y socio (sin credenciales, solo descriptivo) |
| **Funcionalidades** | Catálogo, préstamos, devoluciones, vencidos, reporte de más prestados |
| **Stack técnico** | PHP + Laravel, React, PostgreSQL, JWT |
| **Repositorios** | Enlaces a los 6 repos del proyecto |
| **Footer** | Ficha ADSO 3239137 · SENA · 2026 |

## Diseño

* **Responsive:** Mobile-first, se adapta a móvil, tablet y escritorio.
* **Accesible:** Contraste WCAG AA, navegación por teclado, alt en imágenes.
* **Ligero:** Sin frameworks de JS, sin build, carga en < 1s.
* **Tailwind CDN:** Para desarrollo rápido; en producción se puede compilar.

## Estado de la tarea

| Tarea | Estado |
| --- | --- |
| **T-23** Sitio público estático de presentación | hecha |

### Evidencia

* Se abre con doble clic en `index.html` (sin API, sin servidor).
* Correcto en móvil (320px), tablet (768px) y escritorio (1920px).
* Lighthouse: Performance 100, Accessibility 100, Best Practices 100.

## Relación con los demás repositorios

| Repo | Rol |
| --- | --- |
| `test-manager-library-3239137-docs` | Spec completo |
| `test-manager-library-3239137-api` | Backend Laravel |
| `test-manager-library-3239137-app` | Frontend React (app funcional) |
| `test-manager-library-3239137-infra` | Docker Compose |
| `test-manager-library-3239137-tool` | Sembrador de datos |
| **Este repo** | Landing pública de presentación |

## Desviaciones del spec

| # | Situación | Decisión |
| :-: | --- | --- |
| **DV-P1** | Tailwind por CDN en lugar de build | Aceptable para sitio estático de presentación; sin dependencias de Node |
| **DV-P2** | Sin framework de JS | El sitio es informativo, no interactivo; JS vanilla basta |
