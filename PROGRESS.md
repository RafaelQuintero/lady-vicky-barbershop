# Lady Vicky Barbershop — Rediseño

Proyecto de rediseño de la web de [ladyvickybarbershop.com](https://ladyvickybarbershop.com) en una landing editorial de una sola página, con ambiente de barbería vintage. Todo el contenido y las imágenes son **propios** (descargados, sin depender de la web vieja).

> Objetivo de esta fase: **demo visual** para que Victoria la apruebe. La base de datos (Neon) y la automatización (WhatsApp) van al final.

---

## Estado por fases

| Fase | Qué | Estado |
|---|---|---|
| 0 | Extracción de contenido del sitio (pestaña a pestaña) | ✅ Hecho |
| 0 | Descarga y optimización de imágenes al proyecto | ✅ Hecho |
| 1 | **Demo visual** (landing de una página) | ✅ Listo (en revisión) |
| 1 | Multi-idioma con banderas 🇪🇸 🇬🇧 🇫🇷 | ✅ Listo (en revisión) |
| 2 | Sistema de citas / reservas (demo, sin BBDD) | 🔨 En curso (v1) |
| 3 | Conexión WhatsApp (Skala / Make) | ⏳ Pendiente |
| 4 | Base de datos en Neon (paso final, tras aprobación) | ⏳ Pendiente |

---

## Decisiones tomadas

- **Formato:** un solo `index.html` autónomo + carpeta `assets/` (fácil de ver/compartir para aprobar). Al llegar a reservas migraremos a un proyecto con backend.
- **Imágenes:** 16 descargadas al repo y optimizadas con `sips` (de ~40 MB a ~9,3 MB). Nada de hotlink a la web vieja.
- **Robustez:** progressive enhancement — el contenido es visible aunque el JS no cargue.
- **Idiomas:** ES (por defecto) / EN / FR con selector de banderas. Implementado **vanilla** (sin librería externa), 100% nuestro.
- **Reseñas:** el widget de Google no es extraíble. No inventamos testimonios: mostramos datos reales + botón a las reseñas de Google. Los textos reales se añaden cuando Victoria los facilite.

## Pendiente de confirmar con Victoria

- Horario de lunes, sábado y festivos (la web solo indica **Martes a Viernes, 11:30 a 20:30**).
- Textos reales de reseñas de clientes.
- **Foto-retrato de Victoria** para "Sobre mí" (los assets actuales son decoración del local, no un retrato suyo).
- Si quiere blog (la web actual lo tiene; en la demo no está por ahora).

---

## Marca / Identidad

**Paleta (del logo):**
- Fondo oscuro `#0B0B0B` · Fondo claro `#F5F3EF` · Texto claro `#F5F3EF`
- Acento naranja `#EE7623` (hover `#FF9147`, sobre claro `#C25A10`)
- Poste de barbero: rojo `#E4322B`, azul `#2440C4`, blanco

**Tipografía:** Bodoni Moda (titulares serif, cursiva para énfasis naranja) · Jost (UI, mayúsculas con tracking amplio).

---

## Contenido real (fuente de verdad)

**Servicios**
| Servicio | Precio | Duración |
|---|---|---|
| Corte de pelo | 18 € | 30 min |
| Arreglo de barba | 13 € | 15 min |
| Pack corte + barba | 30 € | 30 min |
| Pack corte + cejas | 25 € | 30 min |
| Diseño de cejas | 7 € | — |

**Negocio**
- Dirección: Calle de las Minas 14, Centro, 28004 Madrid (Malasaña)
- Metro: Noviciado (salida Calle Reyes)
- Horario: Martes a Viernes, 11:30 a 20:30
- WhatsApp: +34 651 59 91 80 → `wa.me/34651599180?text=Hola%21%20Quiero%20una%20cita%2C%20por%20favor`
- Email: ladyvickybarbershop@gmail.com
- Instagram `ladyvicky_barbershop` · Facebook `ladyvickybarbershop` · YouTube `@ladyvickybarbershop`

**Claims**
- Fundadora: Victoria Rodríguez Vega
- +30 años de experiencia · un solo sillón (un cliente por turno) · atención en español, inglés y francés
- Pilares: Experiencia, Exclusividad, Cercanía, Estilo

---

## Estructura de la landing (una página, anclas)

1. Header sticky (logo, nav, banderas, CTA "Reservar cita")
2. Hero split (poste animado, H1, subtítulo, 2 CTAs, metro, 3 stats, foto con etiqueta "Calle Minas 14")
3. Marquee naranja de servicios
4. Servicios (fondo claro, columna sticky + lista de precios con hover invertido)
5. Doble tarjeta Corte / Barba
6. Sobre mí (retrato + texto + firma)
7. Filosofía (4 pilares con hover naranja)
8. Galería (masonry + CTA Instagram)
9. Opiniones (fondo claro, datos + CTA a Google)
10. Contacto (datos + mapa)
11. Footer

---

## Registro de avances

- **2026-07-27** — Extraído todo el contenido del sitio (incl. horario que faltaba). Descargadas y optimizadas 16 imágenes. Creado este MD. Arrancada la Fase 1 (demo visual + multi-idioma).
- **2026-07-27** — Fase 1 completada: landing de 11 secciones construida y verificada en render real (Chrome headless). Selector ES/EN/FR con i18n propio y banderas SVG. Lista para revisión de Victoria.
- **2026-07-27** — Poste de barbero rediseñado con bucle sin costura. Motion añadido (entrada escalonada del hero, reveals con stagger + blur, contador animado, micro-interacciones), respetando reduced-motion. Página `reservas.html` creada: flujo servicio → fecha/hora → datos → confirmar, con resumen en vivo y envío por WhatsApp. Añadido `netlify.toml` para desplegar como sitio estático.
- **2026-07-28** — Sesión de ajustes con feedback de Rafael:
  - ✅ Poste eliminado del hero y de "Sobre mí" (no gustaba).
  - ✅ Fondo cambiado de negro puro a **gris carbón `#232221`**.
  - ✅ Tipografía cambiada a **Playfair Display** (más legible y usada que la Bodoni).
  - ✅ Botón **"Reservar cita" flotante** que aparece al bajar y te sigue.
  - ✅ Banderas de idioma también en **footer** y en la **barra flotante**.
  - ✅ **Auditoría móvil**: hero ajustado, CTAs apiladas, stats en rejilla, galería a 2 columnas, se elimina overflow.
  - ✅ **Naranja de marca corregido a `#cc4f02`** (el del logo/preferencia de Rafael) en toda la web. Nota: el píxel puro del PNG del logo es `#FC6000`; se usa `#cc4f02` por decisión de marca.
  - ✅ **Textos legales reales extraídos** de su web y montados en `legal.html` (Aviso legal, Privacidad, Cookies, Accesibilidad) + enlaces en el footer. Datos: Titular Victoria Rodríguez, NIF 34529217T, C/ Minas 14.
  - ✅ Netlify: creado `netlify.toml` (sitio estático, sin build). Falta hacer `git push` para que despliegue bien.

## Ideas pendientes de Rafael (28 jul) — POR HACER

- ✅ **Scroll horizontal** en la galería (GSAP ScrollTrigger en escritorio; carrusel deslizable en móvil).
- ✅ **Fondos difuminados** (foco de luz suave en el hero).
- ✅ **Desplegado en Netlify** → `vicky-barber.netlify.app` (build vía `package.json` → `dist/`; el `netlify.toml`/UI ejecutan `npm run build`).
- ✅ Arreglos móvil: desbordamiento del hero (`min-width:0`), stats, hover táctil "pegado" (`@media(hover:none)`), animaciones sin `blur` en móvil.
- ⏳ **Ideas de Pinterest**: pendiente (requiere login; tirar de hisbarbería + criterio de diseño).
- ⏳ Pulir títulos de la página legal (numeración romana en mayúsculas).
- ⏳ Revisar bien en móvil real (el headless renderiza a 500px mínimo, no llega a 390px).
