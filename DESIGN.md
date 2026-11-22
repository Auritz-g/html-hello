# Guía de Diseño — AgentHub Admin Panel

## Paleta de colores

Toda la paleta se basa en los tonos **Slate** de Tailwind CSS. Los valores hexadecimales y las clases de Tailwind equivalentes se listan a continuación para modo claro y modo oscuro.

### Fondos generales

| Rol | Modo | Clase Tailwind | Hex | Uso recomendado |
|---|---|---|---|---|
| Fondo general | Claro | `bg-slate-50` | `#F8FAFC` | Fondo principal del panel y `<main>` |
| Fondo general | Oscuro | `dark:bg-slate-950` | `#020617` | Fondo principal del panel y `<main>` |

### Superficies (tarjetas, tablas, modales, sidebar, header)

| Rol | Modo | Clase Tailwind | Hex | Uso recomendado |
|---|---|---|---|---|
| Superficie principal | Claro | `bg-white` | `#FFFFFF` | Tarjetas, tablas, modales, barra lateral y barra superior |
| Superficie principal | Oscuro | `dark:bg-slate-900` | `#0F172A` | Tarjetas, tablas, modales, barra lateral y barra superior |
| Superficie secundaria / Hover | Claro | `bg-slate-100` | `#F1F5F9` | Filas en hover, cabeceras de tabla, zonas colapsables y botones secundarios |
| Superficie secundaria / Hover | Oscuro | `dark:bg-slate-800` | `#1E293B` | Filas en hover, cabeceras de tabla, zonas colapsables y botones secundarios |

### Bordes y divisores

| Rol | Modo | Clase Tailwind | Hex | Uso recomendado |
|---|---|---|---|---|
| Bordes | Claro | `border-slate-200` | `#E2E8F0` | Divisores, bordes de tarjetas, tablas y modales |
| Bordes | Oscuro | `dark:border-slate-800` | `#1E293B` | Divisores, bordes de tarjetas, tablas y modales |

### Texto

| Rol | Modo | Clase Tailwind | Hex | Uso recomendado |
|---|---|---|---|---|
| Texto principal | Claro | `text-slate-900` | `#0F172A` | Títulos, valores numéricos principales y nombres |
| Texto principal | Oscuro | `dark:text-slate-50` | `#F8FAFC` | Títulos, valores numéricos principales y nombres |
| Texto secundario | Claro | `text-slate-600` | `#475569` | Etiquetas, descripciones breves, timestamps y subtítulos |
| Texto secundario | Oscuro | `dark:text-slate-400` | `#94A3B8` | Etiquetas, descripciones breves, timestamps y subtítulos |

### Backdrops (fondos de modales)

| Rol | Modo | Clase Tailwind | Hex / Opacidad | Uso recomendado |
|---|---|---|---|---|
| Backdrop de modales | Claro | `bg-slate-950/60` | `#020617` al 60% | Fondo semitransparente detrás de los modales |
| Backdrop de modales | Oscuro | `dark:bg-black/75` | `#000000` al 75% | Fondo semitransparente detrás de los modales |

### Colores de acento (Dashboard — tarjetas de métrica)

| Métrica | Clase Tailwind | Hex |
|---|---|---|
| Ingresos totales | `bg-blue-500` | `#3B82F6` |
| Pérdidas por descuentos | `bg-orange-500` | `#F97316` |
| Agentes activos | `bg-green-500` | `#22C55E` |
| Agentes fallando | `bg-red-500` | `#EF4444` |

### Colores de estado (badges)

| Estado | Clase Tailwind (fondo) | Clase Tailwind (texto) |
|---|---|---|
| Activo | `bg-green-100` | `text-green-800` |
| Inactivo | `bg-red-100` | `text-red-800` |
| Pendiente | `bg-yellow-100` | `text-yellow-800` |
| Resuelto | `bg-gray-100` | `text-gray-500` |

### Colores de tipo de error (badges)

| Tipo de error | Clase Tailwind (fondo) | Clase Tailwind (texto) |
|---|---|---|
| Crash | `bg-red-100` | `text-red-800` |
| Timeout | `bg-orange-100` | `text-orange-800` |
| API Error | `bg-yellow-100` | `text-yellow-800` |
| Validation | `bg-blue-100` | `text-blue-800` |

### Botón destructivo (Eliminar)

| Elemento | Clase Tailwind |
|---|---|
| Fondo del botón | `bg-red-600` |
| Texto del botón | `text-white` |
| Hover del botón | `hover:bg-red-700` |

### Breakpoints responsivos

| Nombre | Breakpoint (Tailwind) | Descripción |
|---|---|---|
| Móvil / Tablet pequeño | `sm` (≥640px) | Layout de una columna, sidebar colapsada a iconos |
| Tablet / Escritorio pequeño | `lg` (≥1024px) | Sidebar expandida con icono + texto, cuadrículas de 2 columnas |
| Escritorio grande | `xl` (≥1280px) | Layout completo con espacio adicional |

## Tipografía

- **Familia:** Sistema (sin definir una específica, se usa la predeterminada del navegador / Tailwind).
- **Tamaños:**
  - Títulos de sección: `text-2xl font-bold`
  - Valores de métrica: `text-3xl font-bold`
  - Nombres en tablas: `text-sm font-medium`
  - Texto secundario / descripciones: `text-sm text-slate-600` (`dark:text-slate-400`)
  - Badges: `text-xs font-medium`
  - Timestamps: `text-xs text-slate-500`

## Sombras

- Tarjetas de métrica: `shadow-sm`
- Modales: `shadow-xl`
- Dropdowns: `shadow-lg`
- Sidebar: `shadow-md` (solo en modo claro, `shadow-slate-200`)