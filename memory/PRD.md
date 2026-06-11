# Vida de Fe — PRD

## Problema original
Rediseñar visualmente un sitio web católico estático manteniendo todo el contenido pero modernizándolo con tono elegante y espiritual. Paleta dorada + azul profundo + crema/marfil, tipografías serif elegantes, glassmorphism, hover effects, divisores ornamentales, animaciones sutiles, responsive.

## Stack / Arquitectura
- Sitio estático HTML/CSS/JS (sin framework)
- Servido por `serve` desde /app/frontend (puerto 3000) sobre los archivos `/app/index.html`, `/app/style.css`, `/app/papas.json`, `/app/santos.json`, `/app/images/*`.
- Sin backend ni MongoDB (no se requirió).

## Decisiones del usuario
- Código existente reutilizado (sólo rediseño visual).
- Palabra del Día: contenido estático rotativo (versículos predefinidos).
- Contacto: solo visual.
- Imágenes: usar las del repositorio.
- Tema: claro elegante (crema/marfil dominante, dorado, azul profundo).

## Implementado (2026-01)
- **Header glassmorphism** con blur + estado scrolled, logo con anillo cónico dorado, navegación con subrayado animado dorado, CTA con shimmer.
- **Hero "Palabra del Día"**: kicker en mayúsculas, título Playfair Display de 2 líneas (Palabra / del Día en itálica dorada), subtítulo serif itálico, botones (CTA dorado con shimmer + ghost), tarjeta de versículo con doble borde dorado, ornamentos decorativos, icono paloma flotante, indicador de scroll animado, fondo con rayos cónicos animados.
- **Sección Santos**: 3 cards con imagen aspect 3/4, overlay en hover, badge cruz dorada, captions Playfair + itálica dorada.
- **Sección Papas**: 5 cards en grid (5 col desktop, 3/2/1 responsive) con mismo tratamiento + año/periodo.
- **Sección Fe**: blockquote ornamentado con comillas Playfair grandes en dorado + píldoras "Oración / Palabra / Caridad".
- **Sección Contacto**: pill dorado para email + chips decorativos (Testimonios / Colaborar / Sugerencias).
- **Divisores ornamentales** entre secciones (cruz, estrella, paloma) con líneas doradas degradadas.
- **Footer oscuro** (navy gradient + halos dorados): versículo destacado "Yo soy el camino, la verdad y la vida — Juan 14,6", grid de links, "Dios te ama" en gradient dorado con cruces, año dinámico.
- **Popover de biografías** restilizado (flecha, sombras, leer más con CTA dorada) – datos cargados de papas.json/santos.json.
- **Animaciones**: reveal on scroll (IntersectionObserver), floating icons, shimmer botones, hover scale en cards, rotación sutil del anillo del logo.
- **Tipografía**: Playfair Display (títulos), Cormorant Garamond (itálicas decorativas), Inter (cuerpo).
- **Responsive**: desktop / tablet (3 col) / mobile (2 col → 1 col en <460px). Menú móvil con animación tipo scale.
- **data-testid** añadidos a elementos clave (boton-versiculo, nav-*, santo-*, papa-*, versiculo-card, etc.).

## Backlog / Futuro
- P1: Modo oscuro opcional con conmutador en navbar.
- P1: Sección de oración/rosario con audio reproducible.
- P2: Calendario litúrgico con santo del día automatizado.
- P2: Compartir versículo en redes (Twitter/WhatsApp) desde la card.
- P2: PWA / instalable + notificaciones diarias.
