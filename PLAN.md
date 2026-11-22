# AgentHub — Plan de Implementación

> Panel de administración SaaS para gestionar agentes de IA.
> Basado en mockups de Stitch y especificaciones técnicas.

---

## Stack Tecnológico

- **HTML5** — Estructura semántica
- **Tailwind CSS v3** — CDN con configuración personalizada (colores, tipografía)
- **JavaScript vanilla** — Toda la lógica SPA, modales, dropdowns, tema oscuro
- **Sin frameworks, sin backend, sin dependencias adicionales**

---

## Estructura de Archivos

```
html-hello/
├── index.html              # Única página (SPA)
├── icons/                  # 16 SVGs ya existentes
├── stitch_reference/       # 6 HTMLs de referencia (NO modificar)
├── DESIGN.md               # Guía de diseño modo claro
├── DESIGN_DARK.md          # Guía de diseño modo oscuro
├── SPECS.md                # Especificaciones técnicas
├── PROGRESS.md             # Seguimiento de progreso
└── PLAN.md                 # Este archivo
```

---

## Tareas de Implementación

### T1 — Esqueleto Base + Layout Global
**Archivo**: `index.html`

- [ ] Crear estructura HTML con doctype, `<head>` y metadatos
- [ ] Cargar Tailwind CSS vía CDN
- [ ] Configurar colores personalizados Tailwind (AgenteHub colors de DESIGN.md)
- [ ] Configurar tipografía (Inter para textos, JetBrains Mono para código)
- [ ] Layout: Sidebar (izquierda) + Header (superior) + Main (contenido dinámico)
- [ ] Sidebar con logo y 6 ítems de navegación (Dashboard, Usuarios, Agentes, Skills, Contrataciones, Log de Errores)
- [ ] Cada ítem con su icono SVG inline correspondiente desde `icons/`
- [ ] Header con título de sección + toggle modo oscuro + avatar de perfil
- [ ] Estructura responsive inicial

### T2 — Sistema de Datos Hardcodeados
**Archivo**: `index.html` (dentro de `<script>`)

- [ ] Crear objeto global `APP_DATA` con todas las colecciones
- [ ] `APP_DATA.users`: Array de 8-10 usuarios extraídos del Stitch
- [ ] `APP_DATA.agents`: Array de 6-8 agentes extraídos del Stitch
- [ ] `APP_DATA.skills`: Array de skills desde SKILLS.html
- [ ] `APP_DATA.contrataciones`: Array de contratos desde CONTRATACIONES_DE_AGENTES.html
- [ ] `APP_DATA.errorLogs`: Array de errores desde LOG_DE_ERRORES.html
- [ ] `APP_DATA.dashboardMetrics`: Objeto con métricas del dashboard

### T3 — Navegación SPA
**Archivo**: `index.html` (dentro de `<script>`)

- [ ] Función `navigateTo(sectionId)` que muestra/oculta secciones
- [ ] Todas las secciones como `<div>` con clase `hidden` y un `id` único
- [ ] Actualizar clase `active` en sidebar al navegar
- [ ] Actualizar título del header según sección activa
- [ ] Soporte para hash en URL (`#dashboard`, `#usuarios`, etc.)
- [ ] Seleccionar sección desde hash al cargar la página

### T4 — Sistema de Dropdowns
**Archivo**: `index.html` (dentro de `<script>`)

- [ ] Función genérica `toggleDropdown(id)` para mostrar/ocultar cualquier dropdown
- [ ] Cerrar dropdown al hacer clic fuera (event listener en `document`)
- [ ] Cerrar con tecla Escape
- [ ] Aplicar a: dropdown de perfil en header, filtros en tablas

### T5 — Sistema de Modales
**Archivo**: `index.html` (dentro de `<script>`)

- [ ] Modal genérico reutilizable: `openModal(titulo, contenidoHTML)`
- [ ] Modal de confirmación para acciones destructivas: `openConfirmModal(mensaje, onConfirm)`
- [ ] Cerrar modal con clic en X
- [ ] Cerrar modal con clic en backdrop (overlay)
- [ ] Cerrar modal con tecla Escape
- [ ] Animación de entrada/salida con transiciones CSS

### T6 — Dashboard
**Archivo**: `index.html`

- [ ] 4 tarjetas métricas: Total Agentes, Skills Activos, Usuarios Registrados, Contrataciones
- [ ] Cada tarjeta con icono, valor numérico, label y variación porcentual
- [ ] Gráfico de actividad semanal (barras con CSS puro o canvas simple)
- [ ] Enlace rápido a cada sección desde las tarjetas
- [ ] Últimas actividades listadas en timeline

### T7 — Gestión de Usuarios
**Archivo**: `index.html`

- [ ] Tabla con columnas: Nombre, Email, Rol, Estado, Fecha Registro, Acciones
- [ ] Badge de estado (Activo/Inactivo/Pendiente) con colores
- [ ] Badge de rol con colores distintivos
- [ ] Dropdown de acciones por fila (Editar, Eliminar)
- [ ] Modal de edición con formulario precargado
- [ ] Confirmación destructiva para eliminar
- [ ] Botón "Añadir Usuario" con modal de creación

### T8 — Gestión de Agentes
**Archivo**: `index.html`

- [ ] Vista de tarjetas (grid) para cada agente
- [ ] Cada tarjeta: avatar/icono, nombre, descripción, estado, skills asociados
- [ ] Skills colapsables dentro de cada tarjeta (transición suave)
- [ ] Badge de estado (Online/Offline/Error) con indicador de color
- [ ] Botón de acción "Contratar" desde la tarjeta

### T9 — Catálogo de Skills
**Archivo**: `index.html`

- [ ] Catálogo en tarjetas mostrando cada skill
- [ ] Cada tarjeta: icono, nombre, descripción, categoría
- [ ] Filtro por categoría (dropdown o tabs)
- [ ] Búsqueda por nombre (campo de texto)

### T10 — Contrataciones
**Archivo**: `index.html`

- [ ] Tabla con columnas: Agente, Cliente, Fecha Inicio, Fecha Fin, Monto, Estado, Acciones
- [ ] Badge de estado del contrato (Activo/Completado/Cancelado/Pendiente)
- [ ] Formato de moneda para montos
- [ ] Modal de detalle con desglose de precios (tarifa base, impuestos, descuentos, total)
- [ ] Progreso visual del contrato (barra de progreso)

### T11 — Log de Errores
**Archivo**: `index.html`

- [ ] Tabla con columnas: Fecha/Hora, Tipo, Mensaje, Agente, Usuario, Acciones
- [ ] Badge de tipo de error (Warning, Critical, Info) con colores semánticos
- [ ] Badge de severidad con iconos
- [ ] Modal de detalle con stack trace o información completa
- [ ] Filtro por tipo de error (tabs o dropdown)

### T12 — Toggle Modo Oscuro
**Archivo**: `index.html` (dentro de `<script>`)

- [ ] Variable CSS `--color-bg` y derivadas para modo claro/oscuro
- [ ] Toggle en header (icono sol/luna)
- [ ] Persistencia en `localStorage` (`theme = 'light' | 'dark'`)
- [ ] Aplicar clase `dark` al `<html>` para activar estilos oscuros
- [ ] Transición suave entre modos (0.3s ease en colores)
- [ ] Detectar preferencia del sistema (`prefers-color-scheme`) como valor por defecto

### T13 — Integración de Iconos SVG
**Archivo**: `index.html`

- [ ] Mapear nombres de iconos desde Stitch a archivos en `/icons/`
- [ ] Función helper `renderIcon(nombre)` que devuelve SVG inline
- [ ] Reemplazar todos los Material Symbols por SVGs inline
- [ ] Asegurar que los SVGs hereden el color del texto (currentColor)
- [ ] Tamaños consistentes (w-5 h-5 para sidebar, w-6 h-6 para header)

### T14 — Responsividad y Refinamiento Final

- [ ] Sidebar colapsada a iconos en tablet (< 1024px)
- [ ] Menú hamburguesa en móvil (< 640px)
- [ ] Tablas con scroll horizontal en móvil
- [ ] Grid adaptable para tarjetas (1 col en móvil, 2 en tablet, 3+ en desktop)
- [ ] Espaciado y padding consistente en todos los breakpoints
- [ ] Animaciones y transiciones suaves (hover en sidebar, load de secciones)
- [ ] Estados vacíos y de carga para cada sección
- [ ] Prueba manual de navegación completa

---

## Orden de Construcción

Cada tarea depende de la anterior. Ejecutar en este orden:

```
T1  →  T2  →  T12  →  T3  →  T4  →  T5  →  T13
                                               ↓
                              T6  →  T7  →  T8  →  T9  →  T10  →  T11
                                                                      ↓
                                                                    T14
```

**Razonamiento:**
1. **T1** (esqueleto) y **T2** (datos) son la base de todo
2. **T12** (modo oscuro) se integra temprano para trabajar con ambas paletas desde el inicio
3. **T3-T5** (SPA, dropdowns, modales) son la infraestructura interactiva
4. **T13** (iconos) justo antes de las secciones para usarlos directamente
5. **T6-T11** implementan cada sección en orden de complejidad
6. **T14** responsividad y pulido final sobre todo ya construido

---

## Checklist de Progreso

| Tarea | Descripción | Estado |
|-------|-------------|--------|
| T1 | Esqueleto base + Layout global | ⬜ |
| T2 | Datos hardcodeados | ⬜ |
| T3 | Navegación SPA | ⬜ |
| T4 | Sistema de dropdowns | ⬜ |
| T5 | Sistema de modales | ⬜ |
| T6 | Dashboard | ⬜ |
| T7 | Gestión de Usuarios | ⬜ |
| T8 | Gestión de Agentes | ⬜ |
| T9 | Catálogo de Skills | ⬜ |
| T10 | Contrataciones | ⬜ |
| T11 | Log de Errores | ⬜ |
| T12 | Toggle modo oscuro | ⬜ |
| T13 | Integración de iconos SVG | ⬜ |
| T14 | Responsividad y refinamiento | ⬜ |

---

## Notas Técnicas

- **Íconos**: Todos los Material Symbols del Stitch serán reemplazados por los SVGs en `/icons/`
- **Tailwind**: Usar clases utilitarias de Tailwind, no CSS personalizado excepto para animaciones
- **JavaScript**: Una sola etiqueta `<script>` al final del `<body>` con toda la lógica
- **Datos**: Hardcodeados en el JS, sin fetch ni backend
- **Modo oscuro**: Clase `dark` en `<html>` + `localStorage` para persistencia
- **Responsive**: Sidebar colapsable (<1024px), menú hamburguesa (<640px)